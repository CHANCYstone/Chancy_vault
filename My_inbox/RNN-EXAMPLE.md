当然！下面是一个**简单的 RNN（循环神经网络）**的示例，使用 torch 这个 R 语言的深度学习库（基于 PyTorch）。这个示例的任务是对一个简单的时间序列进行预测。

---

**示例：用 RNN 预测简单的时间序列**

  

我们将：

1. 生成一个简单的 **正弦波（sin wave）** 作为数据集

2. 使用 RNN 训练模型

3. 进行预测

  

**安装和加载必要的库**

  

首先，确保你的 R 环境安装了 torch：

```
install.packages("torch")
```

然后，加载 torch 库：

```
library(torch)
```

  

---

**定义 RNN 模型**

```
# 定义 RNN 结构
rnn_model <- nn_module(
  initialize = function(input_size, hidden_size, output_size) {
    self$hidden_size <- hidden_size
    self$rnn <- nn_rnn(input_size, hidden_size, batch_first = TRUE)
    self$fc <- nn_linear(hidden_size, output_size)
  },
  
  forward = function(x) {
    h0 <- torch_zeros(1, x$size(1), self$hidden_size)
    out, _ <- self$rnn(x, h0)
    out <- self$fc(out[ , -1, ])  # 取最后一个时间步的输出
    return(out)
  }
)
```

  

---

**生成数据**

  

我们创建一个简单的**正弦波数据集**：

```
# 生成正弦波数据
set.seed(123)
timesteps <- seq(0, 100, by = 0.1)
data <- sin(timesteps)

# 处理数据成 (samples, time_steps, input_size) 形式
create_sequences <- function(data, seq_length) {
  sequences <- list()
  labels <- list()
  for (i in 1:(length(data) - seq_length)) {
    sequences[[i]] <- array(data[i:(i + seq_length - 1)], dim = c(seq_length, 1))
    labels[[i]] <- array(data[i + seq_length], dim = c(1))
  }
  return(list(x = torch_tensor(do.call(rbind, sequences)), 
              y = torch_tensor(do.call(rbind, labels))))
}

seq_length <- 10  # 时间窗口长度
dataset <- create_sequences(data, seq_length)
```

  

---

**训练模型**

```
# 定义模型和优化器
input_size <- 1
hidden_size <- 16
output_size <- 1
model <- rnn_model(input_size, hidden_size, output_size)

optimizer <- optim_adam(model$parameters, lr = 0.01)
loss_fn <- nn_mse_loss()

# 训练循环
epochs <- 100
for (epoch in 1:epochs) {
  optimizer$zero_grad()
  
  # 计算前向传播
  outputs <- model(dataset$x$unsqueeze(1))
  loss <- loss_fn(outputs, dataset$y)
  
  # 反向传播
  loss$backward()
  optimizer$step()
  
  if (epoch %% 10 == 0) {
    cat(sprintf("Epoch [%d/%d], Loss: %.4f\n", epoch, epochs, loss$item()))
  }
}
```

  

---

**测试模型**

```
# 预测新数据
test_input <- dataset$x[1, , , drop = FALSE]  # 取第一个序列
preds <- c()
for (i in 1:50) {
  pred <- model(test_input$unsqueeze(1))$squeeze()
  preds <- c(preds, pred$item())
  test_input <- torch_cat(list(test_input[ , -1, , drop = FALSE], 
                               pred$unsqueeze(1)$unsqueeze(1)), dim = 2)
}

# 画出预测曲线
library(ggplot2)
plot_data <- data.frame(
  time = 1:length(data),
  true = data
)
plot_pred <- data.frame(
  time = (length(data) - 50):(length(data) - 1),
  pred = preds
)

ggplot(plot_data, aes(x = time, y = true)) +
  geom_line(color = "blue") +
  geom_line(data = plot_pred, aes(x = time, y = pred), color = "red") +
  labs(title = "RNN 预测正弦波", x = "时间步", y = "值")
```

  

---

**解释**

1. **数据预处理**：使用 sin() 生成正弦波数据，并构造 seq_length 个时间步的序列。

2. **RNN 结构**：

• nn_rnn() 是 PyTorch 的标准 RNN 单元。

• nn_linear() 将 RNN 的输出映射到最终预测值。

3. **训练**：

• 通过**均方误差损失（MSE）**训练模型。

• 使用 Adam 优化器进行优化。

4. **预测**：

• 让模型根据之前的 seq_length 预测下一个值，逐步构造完整的未来预测序列。

• 画出**真实数据（蓝色）** vs. **预测数据（红色）**。

---

**结果**

• 运行完后，你会看到 RNN 能够学习到正弦波的模式，并预测未来的值。

• 但如果预测步长较长，误差可能会积累，导致**偏移**。

  

如果你对更复杂的模型（如 LSTM）感兴趣，可以用 nn_lstm() 替换 nn_rnn() 试试看！ 🚀
