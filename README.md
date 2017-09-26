# CBIR
Using BOVW to create a CBIR system
建立该系统一般包含四个步骤：
    从图像库中提取特征点和对应的特征向量
    用k-means算法来建立视觉词典
    通过第二步中建立的视觉词典计算每张图像的视觉词袋
    提取搜索图像的视觉词袋，并用该词袋进行搜索
    
从图像库中提取特征点和对应的特征向量
    detectanddescribe是用来从数据库中的图像提取特征点和对应的特征向量的类（可以使用任意方法）
    rootsift是用来提取rootsift特征向量的类
    baseindexer特征索引的父类
    featureindexer是存储特征点和特征向量的类，提供对HDF5的接口
    
用k-means算法来建立视觉词典
    vocabulary是用来建立视觉词典的类
    
通过第二步中建立的视觉词典计算每张图像的视觉词袋
    BagOfVisualWords是用来建立视觉词袋的类
    BOVWIndexer是用来存储视觉词袋的类（存储到HDF5)

提取搜索图像的视觉词袋，并用该词袋进行搜索
    redisqueue是反向索引的类，用来减少搜索时间
    searcher是搜索类，里面要加上Tf-idf加权来提高搜索精度
    spatialverifier是增加搜索空间信息的类


