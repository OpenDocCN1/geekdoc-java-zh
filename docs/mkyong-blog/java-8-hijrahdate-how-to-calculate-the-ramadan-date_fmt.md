
# Java 8–HijrahDate，如何计算斋月日期

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/java8/java-8-hijrahdate-how-to-calculate-the-ramadan-date/>

[斋月](http://web.archive.org/web/20190225092841/https://en.wikipedia.org/wiki/Ramadan_(calendar_month))是伊斯兰历的第九个月，整月。

## 1. 回历 -> 2016 年斋月

计算 2016 年斋月开始和结束的完整示例

`TestHijrahDate.java`

```java
package com.mkyong.date;

import java.time.LocalDate;
import java.time.chrono.HijrahDate;
import java.time.temporal.ChronoField;
import java.time.temporal.TemporalAdjusters;

public class TestDate {

    public static void main(String[] args) {

        //first day of Ramadan, 9th month
        HijrahDate ramadan = HijrahDate.now()
                .with(ChronoField.DAY_OF_MONTH, 1).with(ChronoField.MONTH_OF_YEAR, 9);
        System.out.println("HijrahDate : " + ramadan);

        //HijrahDate -> LocalDate
        System.out.println("\n--- Ramandan 2016 ---");
        System.out.println("Start : " + LocalDate.from(ramadan));

        //until the end of the month
        System.out.println("End : " + LocalDate.from(ramadan.with(TemporalAdjusters.lastDayOfMonth())));

    }

}
```

输出

```java
HijrahDate : Hijrah-umalqura AH 1437-09-01

--- Ramandan 2016 ---
Start : 2016-06-06
End : 2016-07-05
```

## 参考

1. [维基百科–斋月(日历月)](http://web.archive.org/web/20190225092841/https://en.wikipedia.org/wiki/Ramadan_(calendar_month))
2. [HijrahDate JavaDoc](http://web.archive.org/web/20190225092841/https://docs.oracle.com/javase/8/docs/api/java/time/chrono/HijrahDate.html)

[hijrah](http://web.archive.org/web/20190225092841/http://www.mkyong.com/tag/hijrah/) [java.time](http://web.archive.org/web/20190225092841/http://www.mkyong.com/tag/java-time/) [java8](http://web.archive.org/web/20190225092841/http://www.mkyong.com/tag/java8/) [ramadan](http://web.archive.org/web/20190225092841/http://www.mkyong.com/tag/ramadan/)
