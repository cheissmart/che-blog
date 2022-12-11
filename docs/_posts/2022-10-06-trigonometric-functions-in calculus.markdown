---
layout: post
title:  "Trigonometric functions in calculus"
date:  2022-10-06 11:21:00 +0800
categories: math
tags: [calculus, trigonometric, derivative, integral]
image: combinatorics-on-blackboard.jpg
---
## Intro
I resently discovered that I have forgotten the integral of some trigonometric functions, so I am writing this post to get familiar with those integrals. At the same time, I hope that some readers may find this post helpful.

## Remarks on inverse functions
Many functions that we will discuss($sin$, $cos$, $cosh$, ...) are not bijective, so their inverse functions don't exist. However, because of their periodicity or symmetry, it can be resonable to define their inverse by suitably restricting their domains. For instance, $sin(x)$ is bejective if we restrict its domain to $[-\frac{\pi}{2}, \frac{\pi}{2}]$.

List of inverse of trigonometric functions:
* $sin^{-1}: [-1, 1] \rightarrow [-\frac{\pi}{2}, \frac{\pi}{2}]$

* $cos^{-1}: [-1, 1] \rightarrow [0, \pi]$

* $tan^{-1}: (-\infty, \infty) \rightarrow (-\frac{\pi}{2}, \frac{\pi}{2})$

* $cot^{-1}: (-\infty, \infty) \rightarrow (0, \pi)$

* $sec^{-1}: (-\infty, -1] \cup [1, \infty) \rightarrow [0, \pi] - \\{\frac{\pi}{2}\\}$

* $csc^{-1}: (-\infty, -1] \cup [1, \infty) \rightarrow [-\frac{\pi}{2}, \frac{\pi}{2}] - \\{0\\}$

The **domains** and **ranges** of these functions are important when you are simplifying expressions like
$sin(cos^{-1}(x))$. Because $sin^2(\theta) + cos^2(\theta) = 1$, you can see that $sin^2(cos^{-1}(x)) = 1 - x^2$.
But is $sin(cos^{-1}(x))$ equal to $+\sqrt{1 + x^2}$ or $-\sqrt{1+x^2}$?
To answer this question, you have to inspect the **range** of $cos^{-1}$.
Because $cos^{-1}(x) \in [0, \pi]$, $sin(cos^{-1}(x)) \in [0, 1]$.
So we can conclude that $sin(cos^{-1}(x)) = \sqrt{1 + x^2}$

Here is another example. If you don't inspect the **domains** and **ranges** carefully, you may incorrectly conclude that $tan(sec^{-1}(x)) = \sqrt{x^2-1}$ because $sec^2(\theta) - tan^2(\theta) = 1$. In fact, $tan(sec^{-1}(x)) = \sqrt{x^2-1}\cdot sign(x)$. Try to prove this result yourself.

## Derivatives
To make this post more complete, I will also briefly list out the derivaties of common trigonometry-related functions.

* $\frac{d}{dx} sin(x) = cos(x),\ x \in \mathbb{R}$

* $\frac{d}{dx} cos(x) = -sin(x),\ x \in \mathbb{R}$

* $\frac{d}{dx} tan(x) = sec^2(x),\ x \in \mathbb{R} - \\{ \frac{\pi}{2} + n\pi \lvert n \in \mathbb{Z}\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\frac{d}{dx} tan(x) = \frac{d}{dx} \frac{sin(x)}{cos(x)} = \frac{cos^2(x)+sin^2(x)}{cos^2(x)} = sec^2(x)$
	  		</p>
	</details>

* $\frac{d}{dx} cot(x) = -csc^2(x),\ x \in \mathbb{R} - \\{n\pi \lvert n \in \mathbb{Z}\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\frac{d}{dx} cot(x) = \frac{d}{dx} \frac{cos(x)}{sin(x)} = \frac{-sin^2(x)-cos^2(x)}{sin^2(x)} = -csc^2(x)$
	  		</p>
	</details>

* $\frac{d}{dx} sec(x) = sec(x)tan(x),\ x \in \mathbb{R} - \\{ \frac{\pi}{2} + n\pi \lvert n \in 
\mathbb{Z}\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\frac{d}{dx} sec(x) = \frac{d}{dx} \frac{1}{cos(x)} = -\frac{-sin(x)}{cos^2(x)} = \frac{tan(x)}{cos(x)} = sec(x)tan(x)$
	  		</p>
	</details>

* $\frac{d}{dx} csc(x) = -csc(x)cot(x),\ x \in \mathbb{R} - \\{n\pi \lvert n \in \mathbb{Z}\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\frac{d}{dx} csc(x) = \frac{d}{dx} \frac{1}{sin(x)} = -\frac{cos(x)}{sin^2(x)} = -\frac{cot(x)}{sin(x)} = -csc(x)cot(x)$
	  		</p>
	</details>

* $\frac{d}{dx} sin^{-1}(x) = \frac{1}{\sqrt{1 - x^2}},\ x \in (-1, 1)$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} sin^{-1}(x) = \frac{1}{sin'(sin^{-1}(x))} = \frac{1}{cos(sin^{-1}(x))} = \frac{1}{\sqrt{1-x^2}}$
	  		</p>
	</details>

* $\frac{d}{dx} cos^{-1}(x) = -\frac{1}{\sqrt{1 - x^2}},\ x \in (-1, 1)$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} cos^{-1}(x) = \frac{1}{cos'(cos^{-1}(x))} = \frac{1}{-sin(cos^{-1}(x))} = -\frac{1}{\sqrt{1-x^2}}$
	  		</p>
	</details>

* $\frac{d}{dx} tan^{-1}(x) = \frac{1}{1 + x^2},\ x \in \mathbb{R}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} tan^{-1}(x) = \frac{1}{tan'(tan^{-1}(x))} = \frac{1}{sec^2(tan^{-1}(x))}$
	 			$= cos^2(tan^{-1}(x)) = \frac{1}{1+x^2}$
	  		</p>
	</details>

* $\frac{d}{dx} cot^{-1}(x) = -\frac{1}{1 + x^2},\ x \in \mathbb{R}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} cot^{-1}(x) = \frac{1}{cot'(cot^{-1}(x))} = \frac{1}{-csc^2(cot^{-1}(x))}$
	 			$= -sin^2(cot^{-1}(x)) = -\frac{1}{1+x^2}$
	  		</p>
	</details>

* $\frac{d}{dx} sec^{-1}(x) = \frac{1}{\lvert x \rvert \sqrt{x^2 - 1}},\ x \in \mathbb{R} - [-1, 1]$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} sec^{-1}(x) = \frac{1}{sec'(sec^{-1}(x))} = \frac{1}{sec(sec^{-1}(x))tan(sec^{-1}(x))}$
	 			$ = \frac{1}{x \cdot tan(sec^{-1}(x))} = \frac{1}{\lvert x \rvert \sqrt{x^2-1}}$ <br/>
	 			Note that $tan(sec^{-1}(x)) = \sqrt{x^2-1}\cdot sign(x)$
	  		</p>
	</details>

* $\frac{d}{dx} csc^{-1}(x) = -\frac{1}{\lvert x \rvert \sqrt{x^2 - 1}},\ x \in \mathbb{R} - [-1, 1]$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} csc^{-1}(x) = \frac{1}{csc'(csc^{-1}(x))} = \frac{1}{-csc(csc^{-1}(x))cot(sec^{-1}(x))}$
	 			$ = -\frac{1}{x \cdot cot(csc^{-1}(x))} = -\frac{1}{\lvert x \rvert \sqrt{x^2-1}}$ <br/>
	 			Note that $cot(csc^{-1}(x)) = \sqrt{x^2-1}\cdot sign(x)$
	  		</p>
	</details>

* $\frac{d}{dx} sinh(x) = cosh(x),\ x \in \mathbb{R}$

* $\frac{d}{dx} cosh(x) = sinh(x),\ x \in \mathbb{R}$

* $\frac{d}{dx} tanh(x) = sech^2(x),\ x \in \mathbb{R}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\frac{d}{dx} tanh(x) = \frac{d}{dx} \frac{sinh(x)}{cosh(x)} = \frac{cosh^2(x)-sinh^2(x)}{cosh^2(x)} = sech^2(x)$
	  		</p>
	</details>

* $\frac{d}{dx} coth(x) = -csch^2(x),\ x \in \mathbb{R} - \\{0\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\frac{d}{dx} coth(x) = \frac{d}{dx} \frac{cosh(x)}{sinh(x)} = \frac{sinh^2(x)-cosh^2(x)}{sinh^2(x)} = -csch^2(x)$
	  		</p>
	</details>

* $\frac{d}{dx} sech(x) = -sech(x)tanh(x),\ x \in \mathbb{R}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} sech(x) = \frac{d}{dx} \frac{1}{cosh(x)} = -\frac{sinh(x)}{cosh^2(x)} = -sech(x)tanh(x)$
	  		</p>
	</details>

* $\frac{d}{dx} csch(x) = -csch(x)coth(x),\ x \in \mathbb{R} - \\{0\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} csch(x) = \frac{d}{dx} \frac{1}{sinh(x)} = -\frac{cosh(x)}{sinh^2(x)} = -csch(x)coth(x)$
	  		</p>
	</details>

* $\frac{d}{dx} sinh^{-1}(x) = \frac{1}{\sqrt{x^2+1}},\ x \in \mathbb{R}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} sinh^{-1}(x) = \frac{1}{cosh(sinh^{-1}(x))} = \frac{1}{\sqrt{x^2 + 1}}$
	  		</p>
	</details>

* $\frac{d}{dx} cosh^{-1}(x) = \frac{1}{\sqrt{x^2-1}},\ x \in (1, \infty)$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} cosh^{-1}(x) = \frac{1}{sinh(cosh^{-1}(x))} = \frac{1}{\sqrt{x^2 - 1}}$
	  		</p>
	</details>

* $\frac{d}{dx} tanh^{-1}(x) = \frac{1}{1-x^2},\ x \in (-1, 1)$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} tanh^{-1}(x) = \frac{1}{sech^2(tanh^{-1}(x))} = \frac{1}{1 - x^2}$
	  		</p>
	</details>	

* $\frac{d}{dx} coth^{-1}(x) = \frac{1}{1-x^2},\ x \in \mathbb{R} - [-1, 1]$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} coth^{-1}(x) = \frac{1}{-csch^2(coth^{-1}(x))} = \frac{1}{1 - x^2}$
	  		</p>
	</details>	

* $\frac{d}{dx} sech^{-1}(x) = -\frac{1}{x\sqrt{1-x^2}},\ x \in (0, 1)$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} sech^{-1}(x) = -\frac{1}{sech(sech^{-1}(x))tanh(sech^{-1}(x))} \\= -\frac{1}{x \cdot tanh(sech^{-1}(x))} = -\frac{1}{x\sqrt{1-x^2}}$
	  		</p>
	</details>	

* $\frac{d}{dx} csch^{-1}(x) = -\frac{1}{\lvert x\rvert \sqrt{1+x^2}},\ x \in \mathbb{R} - \\{0\\}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$\frac{d}{dx} csch^{-1}(x) = -\frac{1}{csch(csch^{-1}(x))coth(csch^{-1}(x))} \\= -\frac{1}{x \cdot coth(csch^{-1}(x))} = -\frac{1}{|x|\sqrt{1+x^2}}$
	 			Note that $coth(csch^{-1}(x)) = \sqrt{1+x^2} \cdot sign(x)$
	  		</p>
	</details>

The functions listed above are differentiable at all **interior points** of their domain.

## Integrals

* $\int sin(x) dx = -cos(x) + \mathbb{C}$

* $\int cos(x) dx = sin(x) + \mathbb{C}$

* $\int tan(x) dx = -ln(|cos(x)|) + \mathbb{C}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\int tan(x) dx = \int \frac{sin(x) dx}{cos(x)} = -\int \frac{d(cos(x))}{cos(x)} = -ln(|cos(x)|) + \mathbb{C}$
	  		</p>
	</details>

* $\int cot(x) dx = ln(|sin(x)|) + \mathbb{C}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
				$\int cot(x) dx = \int \frac{cos(x) dx}{sin(x)} = \int \frac{d(sin(x))}{sin(x)} = ln(|sin(x)|) + \mathbb{C}$
	  		</p>
	</details>

* $\int sec(x) dx = ln(|sec(x) + tan(x)|) + \mathbb{C}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$d(sec(x)) = sec(x)tan(x) dx\\
				 d(tan(x)) = sec^2(x) dx\\
				 \Rightarrow d(sec(x) + tan(x)) = sec(x)(sec(x) + tan(x)) dx\\
				 \Rightarrow \frac{d(sec(x) + tan(x))}{sec(x) + tan(x)} = sec(x) dx\\
				 \Rightarrow \int sec(x) dx = \int \frac{d(sec(x) + tan(x))}{sec(x) + tan(x)} = ln(|sec(x) + tan(x)|) + \mathbb{C}$
	  		</p>
	</details>


* $\int csc(x) dx = -ln(|csc(x) + cot(x)|) + \mathbb{C}$
	<details class="details-blue">
		<summary>Proof</summary>
	 		<p>
	 			$d(csc(x)) = -csc(x)cot(x) dx\\
				 d(cot(x)) = -csc^2(x) dx\\
				 \Rightarrow d(csc(x) + cot(x)) = -csc(x)(csc(x) + cot(x)) dx\\
				 \Rightarrow -\frac{d(csc(x) + cot(x))}{csc(x) + cot(x)} = csc(x) dx\\
				 \Rightarrow \int csc(x) dx = -\int \frac{d(csc(x) + cot(x))}{csc(x) + cot(x)} = -ln(|csc(x) + cot(x)|) + \mathbb{C}$
	  		</p>
	</details>

<div class='yellow-warning'>
<b>Integral of inverse functions </b> <br/>
let $y = f^{-1}(x)$. <br/>
$\int f^{-1}(x) dx = xy - \int f(y) dy$ (integration by parts) <br/>
The following results can be shown using this formula.
</div>

* $\int sin^{-1}(x) dx = x\cdot sin^{-1}(x) + \sqrt{1 - x^2} + \mathbb{C}$

* $\int cos^{-1}(x) dx = x\cdot cos^{-1}(x) - \sqrt{1 - x^2} + \mathbb{C}$

* $\int tan^{-1}(x) dx = x \cdot tan^{-1}(x) - \frac{1}{2} ln(1 + x^2) + \mathbb{C}$

* $\int cot^{-1}(x) dx = x \cdot cot^{-1}(x) + \frac{1}{2} ln(1 + x^2)  + \mathbb{C}$

* $\int sec^{-1}(x) dx = x \cdot sec^{-1}(x) - ln(\|x + \sqrt{x^2 - 1}\|) + \mathbb{C}$

* $\int csc^{-1}(x) dx = x \cdot csc^{-1}(x) + ln(\|x + \sqrt{x^2 - 1}\|) + \mathbb{C}$


<div class='red-warning'>
I am too lazy to add the integral of hyperbolic functions now. Maybe I will do it one day.
</div>
<br/>
<div class='yellow-warning'>
<b>Case study</b>:  $\int sin^m(x) cos^n(x) dx, n,m \geq 0$ <br/>
If n or m is <b>odd</b>, we can solve it easily with a u-sub.<br/><br/>
Now, suppose both n and m are <b>even</b>. Then, we can use the following relations to transform the integral into an integral involving powers of $cos(2x)$. <br/>
$sin^2(x) = \frac{1 - cos(2x)}{2}$ <br/>
$cos^2(x) = \frac{1 + cos(2x)}{2}$
</div>

## Postcard

<div class = "postcard">
	<p>
	Today, I would like to share a song: <br/>
	<a href="https://www.youtube.com/watch?v=bCB_nIdN86s" target="_blank">地球上最浪漫的一首歌</a> 
	</p>

	I like its soothing melody.

	<div style="height: 100%; position: relative; font-size: 10px;"> <span style="position: absolute; bottom: 0; right: 0; color: #888888"> <a style="color: #888888" href="https://www.freepik.com/free-vector/stamped-postcard-frame-with-travel-theme_13311480.htm#query=travel%20postcard&position=2&from_view=keyword">Image by rawpixel.com</a> on Freepik </span> </div>
</div>
