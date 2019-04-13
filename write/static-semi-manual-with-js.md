# js半手动数据统计

在日常文章数据统计的过程中,纯手动方式已经难以应付,于是乎,逐步开始了程序介入方式进行统计.

在上一节中,探索利用 `csv` 文件格式进行文章数据统计,本来以为能够应付一阵子,没想到仅仅一天我就放弃了.

原因还不是因为我懒,需要复制文章内容,然后整理成**特定的** `csv` 格式,最后利用已编写的 `java` 工具类进行统计.

在这三步操作中,第一步复制文章内容最简单,第二步整理文章格式最麻烦,第三步编写 `csv` 工具类最技术.

因此,能不能再简单点?懒癌晚期,必须继续寻求新的解决方案.

> 关于如何利用 `csv` 文件处理统计数据,可以参考 [https://snowdreams1006.github.io/static-semi-manual-with-csv.html](https://snowdreams1006.github.io/static-semi-manual-with-csv.html)

## 实现效果

### 慕课手记

> [慕课手记](https://www.imooc.com/u/5224488/articles) : https://www.imooc.com/u/5224488/articles

{% chart %}
{
    "data": {
        "x": "x",
        "columns": [
            [
                "x",
                "2019-04-01",
                "2019-04-02",
                "2019-04-03",
                "2019-04-04",
                "2019-04-05",
                "2019-04-06",
                "2019-04-07",
                "2019-04-08",
                "2019-04-09",
                "2019-04-10",
                "2019-04-11",
                "2019-04-12"
            ],
            [
                "粉丝",
                8,
                8,
                8,
                9,
                9,
                9,
                9,
                9,
                9,
                9,
                9,
                9
            ],
            [
                "阅读量",
                3508,
                3645,
                3650,
                4356,
                4528,
                4864,
                5276,
                5593,
                5872,
                5912,
                6271,
                6400
            ],
            [
                "手记",
                32,
                33,
                34,
                36,
                38,
                39,
                40,
                41,
                42,
                42,
                44,
                44
            ],
            [
                "推荐",
                36,
                36,
                37,
                39,
                41,
                42,
                48,
                49,
                50,
                50,
                52,
                52
            ],
            [
                "积分",
                107,
                118,
                118,
                130,
                130,
                141,
                152,
                173,
                173,
                173,
                194,
                195
            ]
        ],
        "axes": {
            "粉丝": "y2"
        },
        "types": {
            "粉丝": "bar"
        }
    },
    "axis": {
      "x": {
        "type": "timeseries",
        "tick": {
            "format": "%Y-%m-%d"
        }
      },
      "y2": {
        "show": "true",
        "label": { 
          "text": "粉丝",
          "position": "outer-middle"
        }
      } 
    }
}
{% endchart %}

### 简书

> [简书](https://www.jianshu.com/u/577b0d76ab87) : https://www.jianshu.com/u/577b0d76ab87

{% chart %}
{
    "data": {
        "x": "x",
        "columns": [
            [
                "x",
                "2019-04-01",
                "2019-04-02",
                "2019-04-03",
                "2019-04-04",
                "2019-04-05",
                "2019-04-06",
                "2019-04-07",
                "2019-04-08",
                "2019-04-09",
                "2019-04-10",
                "2019-04-11",
                "2019-04-12"
            ],
            [
                "粉丝",
                7,
                7,
                6,
                7,
                6,
                5,
                5,
                5,
                5,
                5,
                5,
                5
            ],
            [
                "阅读量",
                343,
                335,
                342,
                358,
                374,
                443,
                468,
                512,
                548,
                552,
                611,
                624
            ],
            [
                "文章",
                33,
                34,
                35,
                37,
                39,
                40,
                41,
                42,
                43,
                43,
                46,
                46
            ],
            [
                "喜欢",
                57,
                58,
                59,
                60,
                62,
                64,
                65,
                67,
                68,
                68,
                68,
                71,
                71
            ],
            [
                "简书钻",
                27,
                28,
                28,
                9,9
                ,9,
                10,
                10,
                10,
                10,
                11,
                11
            ]
        ],
        "axes": {
            "粉丝": "y2"
        },
        "types": {
            "粉丝": "bar"
        }
    },
    "axis": {
      "x": {
        "type": "timeseries",
        "tick": {
            "format": "%Y-%m-%d"
        }
      },
      "y2": {
        "show": "true",
        "label": { 
          "text": "粉丝",
          "position": "outer-middle"
        }
      }
    }
}
{% endchart %}

### 博客园

> [博客园](https://www.cnblogs.com/snowdreams1006/) : https://www.cnblogs.com/snowdreams1006/

{% chart %}
{
    "data": {
        "x": "x",
        "columns": [
            [
                "x",
                "2019-04-01",
                "2019-04-02",
                "2019-04-03",
                "2019-04-04",
                "2019-04-05",
                "2019-04-06",
                "2019-04-07",
                "2019-04-08",
                "2019-04-09",
                "2019-04-10",
                "2019-04-11",
                "2019-04-12"
            ],
            [
                "粉丝",
                17,
                17,
                17,
                18,
                18,
                18,
                18,
                18,
                18,
                18,
                18,
                18
            ],
            [
                "阅读数",
                3889,
                4096,
                4207,
                4388,
                4411,
                4435,
                4471,
                4728,
                4866,
                4867,
                5189,
                5274
            ],
            [
                "随笔",
                31,
                32,
                33,
                34,
                36,
                38,
                39,
                41,
                41,
                41,
                43,
                43
            ],
            [
                "评论数",
                16,
                16,
                16,
                16,
                16,
                16,
                16,
                16,
                16,
                16,
                16,
                16
            ]
        ],
        "axes": {
            "粉丝": "y2"
        },
        "types": {
            "粉丝": "bar"
        }
    },
    "axis": {
      "x": {
        "type": "timeseries",
        "tick": {
            "format": "%Y-%m-%d"
        }
      },
      "y2": {
        "show": "true",
        "label": {
          "text": "粉丝",
          "position": "outer-middle"
        }
      }
    }
}
{% endchart %}

### 腾讯云社区

> [腾讯云社区](https://cloud.tencent.com/developer/user/2952369/activities) : https://cloud.tencent.com/developer/user/2952369/activities

{% chart %}
{
    "data": {
        "x": "x",
        "columns": [
            [
                "x",
                "2019-04-04",
                "2019-04-05",
                "2019-04-06",
                "2019-04-07",
                "2019-04-08",
                "2019-04-09",
                "2019-04-10",
                "2019-04-11",
                "2019-04-12"
            ],
            [
                "粉丝",
                13,
                13,
                13,
                13,
                13,
                13,
                13,
                13,
                13
            ],
            [
                "阅读量",
                1192,
                1561,
                2131,
                2144,
                2149,
                2158,
                2159,
                2163,
                2165
            ],
            [
                "文章",
                34,
                34,
                34,
                34,
                34,
                34,
                34,
                34,
                34
            ],
            [
                "点赞",
                107,
                108,
                110,
                107,
                107,
                107,
                107,
                107,
                107
            ]
        ],
        "axes": {
            "粉丝": "y2"
        },
        "types": {
            "粉丝": "bar"
        }
    },
    "axis": {
      "x": {
        "type": "timeseries",
        "tick": {
            "format": "%Y-%m-%d"
        }
      },
      "y2": {
        "show": "true",
        "label": {
          "text": "粉丝",
          "position": "outer-middle"
        }
      }
    }
}
{% endchart %}
 
