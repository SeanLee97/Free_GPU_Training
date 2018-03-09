# Free_GPU_Training

如何免费用上Google的Colab提供的GPU运算，**并保存训练好的模型**呢？

* 科学上网环境
* colab教程
  * [Medium教程](https://medium.com/deep-learning-turkey/google-colab-free-gpu-tutorial-e113627b9f5d)
  * [知乎中文教程](https://zhuanlan.zhihu.com/p/33344222)
 
有了上面的工作后，现在重点是如何**并保存训练好的模型**

工具：
* sshpass
* scp
* 服务器

训练好的模型并不能保存在GoogleDriver上提供下载，不过可以将模型压缩然后scp发送到远程服务器。
考虑到是在notebook下，所以在scp时必须要指定密码才可发送，所以用到了sshpass，将密码喂给scp才可发送，以下是安装sshpass，并实现发送过程的语句

```
!apt install sshpass
!sshpass -p "your server password" scp -r -o "StrictHostKeyChecking no" path/to/local/model.zip username@server_ip:/path/to/remote
```
上述语句的-o参数一定不能去掉，去掉可能会发送失败！

如何你功能完成了上述步骤，请一定要：
# Thx Google! Thx Google!
