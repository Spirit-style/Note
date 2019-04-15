#K-近邻算法
1. K-近邻算法采用了测量不同特征值之间的距离方法进行分类。
2. 优点：精度高、对异常值不敏感、无数据输入假定。
3. 确点：计算复杂度高、空间复杂度高。
4. 使用数据范围：数值型 和 标称型
5. 工作原理：存在一个样本数据集合，称作训练数据集，并且样本数据集中每个数据都带有标签，也就是我们知道样本集中每一个数据属于哪个分类。输入没有标签的新数据后，将新数据的每个特征与样本集中数据对应的特征进行比较，然后算法提取样本集中特征最相似的数据（最近临）的分类标签。一般来说，只选取样本数据集中前k个最相似的数据，也就是K-近邻算法k的出处，通常K<=20且为整数。最后选择k个相似数据中出现最多的分类，作为新数据的分类。
6. 一般流程：
>收集数据：可以用任何可用方法
>准备数据：距离计算所需要的数值，最好是结构化的数据格式
>分析数据：可以用任何可用方法
>训练算法：该步骤不适用于K-近邻算法
>测试算法：计算错误率
>使用算法：首先需要输入样本数据和结构化的输出结果，然后运行k-近邻算法判定输入数据分别属于哪个分类，最后应用对计算出的分类执行后续出理
7. 算法伪代码：
    >计算已知类别数据集中的点与当前点之间的距离
    >按照距离递增排序
    >选取与当前点距离最小k个点
    >确定前k个点所在类别的出现频率
    >返回前k个点出现频率最高的类别作为当前点的预测分类

8. 示例代码：
```py
from numpy import *
import operator


def createDateSet():
    group = array([[1.0, 1.1], [1.0, 1.0], [0, 0], [0, 0.1]])
    labels = ['A', 'A', 'B', 'B']
    return group, labels


def classify0(inx, dataSet, labels, k): #输入向量inx，训练集，标签，k
    dataSetSize = dataSet.shape[0]      #得到数据集的数量
    diffMat = tile(inx, (dataSetSize, 1)) - dataSet #与数据集每一项作差
    sqDiffMat = diffMat ** 2 #取各个属性差平方
    sqDistances = sqDiffMat.sum(axis=1) #取各个属性值差平方的和
    distances = sqDistances ** 0.5 #开根号
    sortedDistIndicies = distances.argsort() #将distances中的元素从小到大排列，提取其对应的index(索引)，然后输出到
    classCount = {}
    for i in range(k):
        voteIlabel=labels[sortedDistIndicies[i]] #取对应位置的标签
        classCount[voteIlabel]=classCount.get(voteIlabel,0)+1 #以标签为键构造字典
    sortedClassCount=sorted(classCount.items(),key=operator.itemgetter(1),reverse=True)
    return sortedClassCount[0][0]
 ```
9. 涉及的函数：
> tile(inx, (dataSetSize, 1)) 重复构造数组
> sum(axis= ) 无参数时全加，axis=0，按列相加；axis=1，按行相加。
> distances.argsort() #将distances中的元素从小到大排列，提取其对应的index(索引)，然后输出到
>range(start, stop[, step])
    参数说明：
    start: 计数从 start 开始。默认是从 0 开始。例如range（5）等价于range（0， 5）;
    stop: 计数到 stop 结束，但不包括 stop。例如：range（0， 5） 是[0, 1, 2, 3, 4]没有5
    step：步长，默认为1。例如：range（0， 5） 等价于 range(0, 5, 1)

