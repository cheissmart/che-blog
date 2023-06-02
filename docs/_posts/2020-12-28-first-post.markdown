---
layout: post
title:  "First post"
date:  2020-12-28 00:05:07 +0800
categories: general
image: mountains.jpg
---

## Basic Formatting
With Markdown, it is possible to emphasize words by making them  *italicized*, using astericks or underscores, or making them **bold**, using double astericks or double underscores. Of course, you can combine those two formats, with both ***bold and italicized*** text, using any combination of the above syntax. You can also add a strikethrough to text using a double ~~tilde~~.

## Heading
# Heading One(H1)
## Heading Two(H2)
### Heading Three(H3)
#### Heading Four(H4)
##### Heading Five(H5)
###### Heading Six(H6)

## Blockquotes
> This quote may be very useful.

## Code and Syntax Highlighting
It is possible to do `inline code blocks`.

```cpp
#include <bits/stdc++.h>
#define IO_OP std::ios::sync_with_stdio(0); std::cin.tie(0);
#define F first
#define S second
#define V vector
#define PB push_back
#define MP make_pair
#define EB emplace_back
#define ALL(v) (v).begin(), (v).end()
#define debug(x) cerr << "Line(" << __LINE__ << ") -> " << #x << " is " << x << endl

using namespace std;

typedef long long ll;
typedef pair<int, int> pi;
typedef V<int> vi;

const int INF = 1e9 + 7;

signed main()
{
    IO_OP;
	
}


```

## MathJax 
The [Schrödinger equation](https://www.wikiwand.com/en/Schr%C3%B6dinger_equation) is a partial differential equation that describes how the quantum state of a quantum system changes with time: 
<center>
$$
i\hbar\frac{\partial}{\partial t} \Psi(\mathbf{r},t) = \left [ \frac{-\hbar^2}{2\mu}\nabla^2 + V(\mathbf{r},t)\right ] \Psi(\mathbf{r},t)
$$
</center>

Thanks for reading.
