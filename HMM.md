# HMM
## 参考
- [参考一](http://www.cnblogs.com/skyme/p/4651331.html)
- [参考二](http://www.hankcs.com/nlp/hmm-and-segmentation-tagging-named-entity-recognition.html)

## 熵
- 用来表征系统的无序程度。熵越大，系统越无序。
- 最大熵，保留全部的不确定性。

## HMM
### 基础
- 可见状态链
- 隐含状态链，马尔科夫链，隐含状态之间存在转换概率（transition probability）。
- 隐含状态和可见状态之间存在输出概率（emission probability）。
- 五元组

		obs：观测序列
		states：隐状态
		start_p：初始概率（隐状态)
		trans_p：转移概率（隐状态）
		emit_p：发射概率（隐状态表现为显状态的概率）
		
	![](http://images0.cnblogs.com/blog/133059/201507/161450524231771.jpg)
	
	伪码如下：
	
	```
	states = ('Rainy', 'Sunny')
 
	observations = ('walk', 'shop', 'clean')
	 
	start_probability = {'Rainy': 0.6, 'Sunny': 0.4}
	 
	transition_probability = {
	    'Rainy' : {'Rainy': 0.7, 'Sunny': 0.3},
	    'Sunny' : {'Rainy': 0.4, 'Sunny': 0.6},
	    }
	 
	emission_probability = {
	    'Rainy' : {'walk': 0.1, 'shop': 0.4, 'clean': 0.5},
	    'Sunny' : {'walk': 0.6, 'shop': 0.3, 'clean': 0.1},
	}
	```

### 三种问题
- 已知隐含状态数量，转换概率，可见状态链，求隐含状态连。
	- 语音识别，解码问题。
	- 最大似然状态路径。
		- 产生观测结果的概率最大。
		- Viterbi
	- 每一个。
- 已知隐含状态数量，转换概率，可见状态链，求可见状态连产生概率。
	- 检测观察结果与模型是否吻合。
	- 前向算法。
- 已知隐含状态数量，可见状态链，求转换概率。
	- 最常见，很多时候我们只有可见结果，不知道 HMM 模型里的参数，需要从可见结果中估计出这些参数。

### 其他
- 了解算法，会其意，知其形。












