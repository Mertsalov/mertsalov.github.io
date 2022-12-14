---
layout: post
mathjax: true
title:  "Задачи [Векторный анализ]"
date:   2022-12-12 12:07:25 +0000
---

## Задача 1.1

<p style='text-align: justify;'> Доказать теорему косинусов в треугольнике. <a href="https://ru.wikipedia.org/wiki/Теорема_косинусов">Теорема косинусов</a> &mdash; теорема евклидовой геометрии, обобщающая теорему Пифагора на произвольные плоские треугольники. Формулировка: для плоского треугольника со сторонами $a,\,b,\,c$ и углом 
$\gamma$, противолежащим стороне $c$, справедливо соотношение:</p>

$$
c^2 = a^2 + b^2 - 2\cdot a\cdot b\cdot\cos\gamma.
$$

![png]({{ "/assets/images/output_2_0.png" }})

**Решение**

<p style='text-align: justify;'> Изобразим стороны треугольника $ABC$ в виде векторов $AB\equiv\mathbf c,\;AC\equiv\mathbf b,\;CB\equiv\mathbf a$. Тогда $\mathbf a + \mathbf b = \mathbf c$. Возведем это выражение в квадрат:</p>

$$
a^2 + b^2 + 2\cdot\mathbf a\cdot\mathbf b = c^2.
$$

<p style='text-align: justify;'> Используя понятие скалярного произведения, получим $\mathbf a\cdot\mathbf b = a\cdot b\cdot\cos\left(\mathbf a,\mathbf b\right) = a\cdot b\cdot\cos\left(\pi-\gamma\right) = -a\cdot b\cdot\cos\left(\gamma\right)$, где $\gamma = \angle ACB$. Таким образом, $c^2 = a^2 + b^2 - 2\cdot a\cdot b\cdot\cos\gamma$.</p>

## Задача 1.2

<p style='text-align: justify;'> Доказать, что $\cos(\alpha - \beta) = \cos\alpha\cos\beta + \sin\alpha\sin\beta.$</p>

**Решение**

<p style='text-align: justify;'> Пусть даны числа $\alpha$ и $\beta$. Рассмотрим на тригонометрической окружности единичного радиуса точку $A$, соответствующую числу $\alpha$, и точку $B$, соответствующую числу $\beta$. Обозначим начало координат
буквой $Z$ и рассмотрим векторы $\mathbf{a} = \vec{ZA}$, $\mathbf{b} = \vec{ZB}$ (см. следующий рисунок).</p>


```python
Image("images/problem_01_02.png", retina=True)
```

![png]({{ "/assets/images/output_5_0.png" }})

<p style='text-align: justify;'> Из определения тригонометрических функций ясно, что координаты векторов $\mathbf a$ и $\mathbf b$ таковы: $\mathbf a = \left(\cos\alpha, \sin\alpha\right)$, $\mathbf b = \left(\cos\beta, \sin\beta\right)$. Стало быть, скалярное произведение векторов $\mathbf a$ и $\mathbf b$ равно</p>

$$
\mathbf a\cdot\mathbf b = \cos\alpha\cos\beta + \sin\alpha\sin\beta.
$$

<p style='text-align: justify;'> С другой стороны, длина каждого из векторов $\mathbf a$ и $\mathbf b$ равна единице, а угол между ними равен $\alpha - \beta$ (точнее говоря, $\left(\alpha - \beta\right) + 2\pi n$
для некоторого целого $n$, так как число $\alpha - \beta$ может оказаться отрицательным или большим $\pi$). Так или иначе косинус угла между векторами $\mathbf a$ и $\mathbf b$ равен $\cos\left(\alpha - \beta\right)$, так что </p>

$$
\mathbf a\cdot\mathbf b = |\mathbf a|\cdot|\mathbf b|\cdot\cos\left(\alpha - \beta\right)
$$.

<p style='text-align: justify;'> Сопоставляя два выражения для $\mathbf a\cdot\mathbf b$, получаем:</p>

$$
\cos\left(\alpha - \beta\right) = \cos\alpha\cos\beta + \sin\alpha\sin\beta.
$$

<p style='text-align: justify;'> Чтобы получить теперь формулу для косинуса суммы, надо в формулу для $\cos\left(\alpha - \beta\right)$ подставить $-\beta$ вместо $\beta$:</p>

$$
\begin{align*}
\cos\left(\alpha + \beta\right) &= \cos\left(\alpha - (-\beta)\right) = \\
&= \cos\alpha\cos(-\beta) + \sin\alpha\sin(-\beta) = \\
&= \cos\alpha\cos\beta - \sin\alpha\sin\beta.
\end{align*}
$$

<p style='text-align: justify;'> Чтобы получить формулы для синуса суммы и разности, воспользуемся формулами приведения. Вот формула синуса суммы:</p>

$$
\begin{align*}
\sin\left(\alpha + \beta\right) &= \cos\left(\pi/2 - (\alpha + \beta)\right) = \\
&= \cos\left((\pi/2-\alpha) - \beta\right) = \\
&= \cos\left(\pi/2-\alpha\right)\cos\beta + \sin\left(\pi/2-\alpha\right)\sin\beta = \\
&= \sin\alpha\cos\beta + \cos\alpha\sin\beta.
\end{align*}
$$

<p style='text-align: justify;'> Аналогичным способом получается и формула синуса разности.</p>

## Задача 1.3

<p style='text-align: justify;'> Вывести основные формулы сферической тригонометрии.</p>

**Решение**

<p style='text-align: justify;'> Возьмем на сфере единичного радиуса сферический треугольник $ABC$ (см. следующий рисунок), высекаемый трехгранным углом $OABC$. Пусть $\alpha,\;\beta,\;\gamma$ &mdash; углы этого тре­ угольника, а длины его сторон равны $a,\;b,\;c$. Поскольку радиус сферы равен единице, то $a$ равно плоскому углу $\angle BOC$, $b$ &mdash; плоскому углу $\angle AOC$ и $c$ &mdash; плоскому углу $\angle AOB$.</p>

<p style='text-align: justify;'> Установим зависимость между углами $\alpha,\;\beta,\;\gamma$ сферического треугольника и его сторонами $a,\;b,\;c$ (плоскими углами трехгранного угла $OABC$).</p>

<p style='text-align: justify;'> Введем единичные векторы $\mathbf e_1,\;\mathbf e_3,\;\mathbf e_3$, направленные из центра сферы к вершинам сферического треугольника.</p>


```python
Image("images/problem_01_03.png", retina=True)
```

![png]({{ "/assets/images/output_8_0.png" }})

<p style='text-align: justify;'> Угол между плоскостями $OAC$ и $OAB$ (угол $\alpha$) равен углу между нормалями к этим плоскостям. Поэтому</p>

$$
\cos\alpha = \frac{\left(\mathbf e_1\times\mathbf e_2\right)\cdot\left(\mathbf e_1\times\mathbf e_3\right)}{|\mathbf e_1\times\mathbf e_2|\cdot|\mathbf e_1\times\mathbf e_3|}
$$

<p style='text-align: justify;'> Переставляя в смешанном произведении числителя сомножители $\left(\mathbf a \times \mathbf b\right)\cdot\mathbf c = \left(\mathbf c \times \mathbf a\right)\cdot\mathbf b = \left(\mathbf b \times \mathbf c\right)\cdot\mathbf a$ и раскрывая двойное векторное произведение по формуле $\mathbf a \times(\mathbf b \times \mathbf c) = \mathbf b\,(\mathbf a\cdot \mathbf c) - \mathbf c\,(\mathbf a\cdot \mathbf b)$, а также учитывая, что</p>

$$
|\mathbf e_1\times\mathbf e_2| = \sin b,\quad |\mathbf e_1\times\mathbf e_3| = \sin c,
$$

получим

$$
\begin{align*}
\cos\alpha &= \frac{\mathbf e_1\cdot\left[\mathbf e_2\times\left(\mathbf e_1\times\mathbf e_3\right)\right]}{\sin b\cdot\sin c} = \\
\
&= \frac{\mathbf e_1\cdot\left[\mathbf e_1\,(\mathbf e_2\cdot \mathbf e_3) - \mathbf e_3\,(\mathbf e_2\cdot \mathbf e_1)\right]}{\sin b\cdot\sin c} = \\
\
&= \frac{\cos a - \cos c\cdot\cos b}{\sin b\cdot\sin c}.
\end{align*}
$$

Отсюда имеем

$$
\cos a = \cos b\cdot\cos c + \sin b\cdot \sin c\cdot\cos\alpha.
$$

<p style='text-align: justify;'> Совершенно аналогично находим формулы</p>

$$
\begin{align*}
\cos b = \cos c\cdot\cos a + \sin c\cdot \sin a\cdot\cos\beta,\\
\cos c = \cos a\cdot\cos b + \sin a\cdot \sin b\cdot\cos\gamma.
\end{align*}
$$

<p style='text-align: justify;'> Вторую группу формул получим, вычисляя синусы углов $\alpha,\;\beta,\;\gamma$.</p>

Предварительно заметим, что

$$
\begin{align*}
(\mathbf a \times \mathbf b)\times(\mathbf c \times \mathbf d) &= \mathbf b\cdot(\mathbf a\cdot(\mathbf c \times \mathbf d)) - \mathbf a\cdot(\mathbf b\cdot(\mathbf c \times \mathbf d)),\\
\\
(\mathbf a \times \mathbf b)\times(\mathbf a \times \mathbf c) &= \mathbf b\cdot(\mathbf a\cdot(\mathbf a \times \mathbf c)) - \mathbf a\cdot(\mathbf b\cdot(\mathbf a \times \mathbf c)) = \\
&= - \mathbf a\cdot(\mathbf b\cdot(\mathbf a \times \mathbf c)) = \\
&= \mathbf a\cdot(\mathbf b\cdot(\mathbf c \times \mathbf a)) = \\
&= \mathbf a\cdot(\mathbf a\cdot(\mathbf b \times \mathbf c)).
\end{align*}
$$

$$
\begin{align*}
\sin\alpha &= \frac{|\left(\mathbf e_1\times\mathbf e_2\right)\times\left(\mathbf e_1\times\mathbf e_3\right)|}{|\mathbf e_1\times\mathbf e_2|\cdot|\mathbf e_1\times\mathbf e_3|} = \\
\
&= \frac{\big|\,(\mathbf e_1\cdot(\mathbf e_2 \times \mathbf e_3))\;\mathbf e_1\,\big|}{\sin b\cdot\sin c} = \\
\
&= \frac{\big|\,(\mathbf e_1\cdot(\mathbf e_2 \times \mathbf e_3))\,\big|}{\sin b\cdot\sin c}.
\end{align*}
$$

$$
\begin{align*}
\sin\beta &= \frac{|\left(\mathbf e_3\times\mathbf e_1\right)\times\left(\mathbf e_3\times\mathbf e_2\right)|}{|\mathbf e_3\times\mathbf e_1|\cdot|\mathbf e_3\times\mathbf e_2|} = \\
\
&= \frac{\big|\,(\mathbf e_3\cdot(\mathbf e_1 \times \mathbf e_2))\;\mathbf e_3\,\big|}{\sin c\cdot\sin a} = \\
\
&= \frac{\big|\,(\mathbf e_3\cdot(\mathbf e_1 \times \mathbf e_2))\,\big|}{\sin c\cdot\sin a}.
\end{align*}
$$

$$
\begin{align*}
\sin\gamma &= \frac{|\left(\mathbf e_2\times\mathbf e_1\right)\times\left(\mathbf e_2\times\mathbf e_3\right)|}{|\mathbf e_2\times\mathbf e_1|\cdot|\mathbf e_2\times\mathbf e_3|} = \\
\
&= \frac{\big|\,(\mathbf e_2\cdot(\mathbf e_1 \times \mathbf e_3))\;\mathbf e_2\,\big|}{\sin b\cdot\sin a} = \\
\
&= \frac{\big|\,(\mathbf e_2\cdot(\mathbf e_1 \times \mathbf e_3))\,\big|}{\sin b\cdot\sin a}.
\end{align*}
$$

<p style='text-align: justify;'> Заметим, что векторно-скалярное произведение, стоящее в числителе каждого выражения $OA\cdot(OC \times OB) = \mathbf e_1\cdot(\mathbf e_2 \times \mathbf e_3)$ &mdash; это объем параллелепипеда, образованного векторами положения вершин сферического треугольника $OA$, $OB$ и $OC$ в системе координат с центром в точке $O$. Этот объем инвариантен относительно конкретной системы координат, используемой для представления $OA$, $OB$ и $OC$. Поэтому</p>

$$
\sin\alpha\cdot\sin b\cdot\sin c = \sin\beta\cdot\sin c\cdot\sin a = \sin\gamma\cdot\sin b\cdot\sin a
$$

Откуда

$$
\frac{\sin\alpha}{\sin a} = \frac{\sin\beta}{\sin b} = \frac{\sin\gamma}{\sin c}
$$
