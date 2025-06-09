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