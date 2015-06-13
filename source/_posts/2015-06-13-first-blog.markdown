---
layout: post
title: "第一篇博客"
date: 2015-06-13 08:25:27 +0800
comments: true
categories: research
---
# 这是我的第一篇文章

> 知世故而不世故，知人性而包容万物。

本博客包含以下技术内容：
## 大数据&&并行
- Hadoop
- Spark
- Storm
## 科研
- 机器学习
- 自然语言处理
- 计算机视觉
## JAVA代码
``` java
import java.nio.channels.FileChannel;

public interface CallbackInterface(){
    public void dothings();
    public void exeMethods();
}

public class Server1 {
    
    public static void main(String[] args) {
        // TODO Auto-generated method stub
        System.out.println("hello world!!!");
    }

}

```
## Python代码
``` python
import numpy as np
import scipy.sparse
import scipy.optimize

def softmax_cost(theta, num_classes, input_size, lambda_, data, labels):
    """
    :param theta:
    :param num_classes: the number of classes
    :param input_size: the size N of input vector
    :param lambda_: weight decay parameter
    :param data: the N x M input matrix, where each column corresponds
                 a single test set
    :param labels: an M x 1 matrix containing the labels for the input data
    """
    m = data.shape[1]
    theta = theta.reshape(num_classes, input_size)
    theta_data = theta.dot(data)
    theta_data = theta_data - np.max(theta_data)
    prob_data = np.exp(theta_data) / np.sum(np.exp(theta_data), axis=0)
    indicator = scipy.sparse.csr_matrix((np.ones(m), (labels, np.array(range(m)))))
    indicator = np.array(indicator.todense())
    cost = (-1 / m) * np.sum(indicator * np.log(prob_data)) + (lambda_ / 2) * np.sum(theta * theta)
    grad = (-1 / m) * (indicator - prob_data).dot(data.transpose()) + lambda_ * theta
    return cost, grad.flatten()
```
## C/C++ 代码
``` cpp
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>
#include <pthread.h>

#define MAX_STRING 100
#define EXP_TABLE_SIZE 1000
#define MAX_EXP 6
#define MAX_SENTENCE_LENGTH 1000
#define MAX_CODE_LENGTH 40

const int vocab_hash_size = 30000000;  // Maximum 30 * 0.7 = 21M words in the vocabulary

typedef float real;                    // Precision of float numbers

struct vocab_word {
  long long cn;
  int *point;
  char *word, *code, codelen;
};
void InitUnigramTable() {
  int a, i;
  double train_words_pow = 0;
  double d1, power = 0.75;
  table = (int *)malloc(table_size * sizeof(int));
  for (a = 0; a < vocab_size; a++) 
    train_words_pow += pow(vocab[a].cn, power);
  i = 0;
  d1 = pow(vocab[i].cn, power) / train_words_pow;
  for (a = 0; a < table_size; a++) {
    table[a] = i;
    if (a / (double)table_size > d1) {
      i++;
      d1 += pow(vocab[i].cn, power) / train_words_pow;
    }
    if (i >= vocab_size) i = vocab_size - 1;
  }
}
```

## Shell
``` shell
#!/bin/bash
# Program:
#       This program shows "Hello World!" in your screen.
# History:
# 2005/08/23    VBird   First release
PATH=/bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin:~/bin
export PATH
echo -e "Hello World! \a \n"
exit 0
```

## 我的爱好

### Alizee1
{% img /images/alizee1.jpg %}  

### Alizee2
{% img /images/alizee2.jpg %}  
加cap之后：  
{% imgcap left /images/alizee2.jpg Alizee in China %}
