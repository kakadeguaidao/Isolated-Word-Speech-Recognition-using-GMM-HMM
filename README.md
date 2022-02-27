# 使用GMM-HMM完成孤立词的语音识别
使用混合高斯隐马尔可夫模型完成的14个孤立词的语音识别，其中每个孤立词使用4个HMM建模，每个HMM由3个GMM组成，假设高斯分布中各个维度相互独立

采用librosa模块进行MFCC音频特征提取，MFCC系数阶数取12，同时计算MFCC的差分项，因此GMM的维度是24，

采用viterbi法进行音频的对齐

概率密度函数的计算公式采用的是


<img src="https://latex.codecogs.com/svg.image?\frac{1}{2\pi&space;^{d/2}\times\left|&space;\sigma&space;\right|&space;&space;^{1/2}}\times&space;e^{-\frac{1}{2}}\left&space;(&space;X-&space;\mu&space;\right&space;)^{T}\sigma^{-1}\left&space;(&space;X-\mu&space;&space;\right&space;)" title="\frac{1}{2\pi ^{d/2}\times\left| \sigma \right| ^{1/2}}\times e^{-\frac{1}{2}}\left ( X- \mu \right )^{T}\sigma^{-1}\left ( X-\mu \right )" />

训练好的模型（14个HMM-GMM）储存在models.npy文件中
