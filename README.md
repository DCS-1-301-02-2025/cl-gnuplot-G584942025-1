# Gnuplot

$y=sin(x)，tan^{-1}(x)$ のグラフを描く

```gnuplot {cmd=true output="html"}
set terminal svg

plot sin(x),atan(x)
```
関数のプロット
```gnuplot {cmd=true output="html"}
set terminal svg
f2(x) = x * log(x)
reset
set title "関数のプロット"
set xlabel "x"
set ylabel "y"
set xrange [0:7]
set yrange [-20:15]
set grid
set key outside
f1(x) = 2*x**2*sqrt(x)-5*x**2
f2(x) = x/log(x)
plot f1(x) title "f1(x)", f2(x) title "f2(x)"
```
八王子の気温
```gnuplot {cmd=true output="html"}
set terminal svg
set xdata time
set timefmt '%Y/%m/%d'
set xtics format "%m/%d"
set datafile separator ","
set title "八王子の気温（過去一年間）"
set ylabel "温度"
set grid
set key outside
plot "weather2025.csv" using 1:2 w l title "最高気温" , "weather2025.csv" using 1:3 w l title "最高気温（平年）" , "weather2025.csv" using 1:4 w l title "最低気温" , "weather2025.csv" using 1:5 with lines title "最低気温（平年）" 
```
誕生月
```gnuplot {cmd=true output="html"}
set terminal svg
set title "誕生日の月別人数"
set ylabel "人"
set yrange [0:16]
set style fill solid 1.0 border -1
set boxwidth 0.6
set style data boxes
set grid ytics

# 月名ラベルを x 軸に表示
set xtics ("1月" 1, "2月" 2, "3月" 3, "4月" 4, "5月" 5, "6月" 6, \
           "7月" 7, "8月" 8, "9月" 9, "10月" 10, "11月" 11, "12月" 12)

plot "bm.txt" using 1:2 lc rgb "skyblue" notitle
