# 添加显示
1. tf.summary.scalar(name, 标量, collections=None)
2. tf.summary.histogram(tags, values, collections=None, name=None) 
3. tf.summary.image(name, tensor, max_outputs=3, collections=None)


# 保存信息到磁盘
1.  merge\_summary = tf.summary.merge\_all()全部添加
2.  tf.summary.merge([info1, info2,...], collections=None, name=None)

# 指定一个文件用来保存图
1. train_writer = tf.summary.FileWritter(dir,sess.graph)

# 记录训练过程
1. train\_summary = sess.run(merge\_summary,feed_dict =  {...})
2. train\_writer.add\_summary(train\_summary,step)

# 开启tensorborad
1. tensorboard --logdir=/summary\_dir
2. localhost:6006