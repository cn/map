统计用区划代码
============

## 数据来源
[http://www.stats.gov.cn/tjsj/tjbz/tjyqhdmhcxhfdm/](http://www.stats.gov.cn/tjsj/tjbz/tjyqhdmhcxhfdm/)

## 可视化Demo
Demo：[http://phyng.com/scrapy-stats/](http://phyng.com/scrapy-stats/)

## 数据统计
以2013年最新版为例

layer |count(code)| name     
------|-----------|------------
1     | 31        | 省/市/自治区
2     | 345       | 市
3     | 2856      | 县/区
4     | 43854     | 乡/镇/街道
5     | 694688    | 村/居委会

## 数据结构
编码规则：[http://www.stats.gov.cn/tjsj/tjbz/200911/t20091125_8667.html](http://www.stats.gov.cn/tjsj/tjbz/200911/t20091125_8667.html)

`zoning_code_2013.json` 结构：

~~~json
{  
  "name":"中国",
  "children":[  
    {  
      "name":"北京市",#行政层级1
      "code":11,
      "children":[  
        {  
          "name":"市辖区",#行政层级2
          "code":1101,
          "children":[  
            {  
              "name":"东城区",#行政层级3
              "code":110101,
              "children":[  
                {  
                  "name":"东华门街道办事处",#行政层级4
                  "code":110101001,
                  "children":[  
                    {  
                      "name":"多福巷社区居委会",#行政层级5
                      "code":110101001001,
                      "code2":111
                    }
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
~~~

