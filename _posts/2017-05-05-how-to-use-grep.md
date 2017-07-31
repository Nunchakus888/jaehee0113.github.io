---
layout: post
title: "how to use grep"
category:
date: 2017-05-05
comments: true
disqus_identifier: 96e34dfeaabb88c3
highlights: false
---

<pre>
  <code> Unix 기반의 시스템의 설명입니다 </code>
</pre>

<h1> 배경 </h1>

Unix 기반 환경에서 server troubleshooting을 할 때 가장 기본적으로 쓰이는 명령어 중에 하나이다. grep 은 "<b>g</b>lobal search for <b>re</b>gular expression and <b>p</b>rint all lines containing it" 의 약자라고 생각하면 되겠다. 억지라고 생각하면 그렇지만 사실 읽기 쉽지 않은가? 그랩! 말그대로 grab (갖고 오다) 라가 연상되는 명령어로써 참 직관적이라고 생각한다.

Grep과 함께 pipeline 컨셉을 이해하여야 한다. 이 건, 단순히 여기서만 나오는게 아니라 대부분의 프로그래밍 언어에서도 항상 쓴다. 그러니 나중을 위해 꼭 이해하고 있도록 하자.

<h1> Pipe (또는 Pipeline) </h1>

Pipe 는 <b>|</b> 기호를 쓴다. 이 기호는 } 키 옆에 있는 (Shift 누르고) 그 키이다. Pipe의 기본 개념은 명령어 들을 체인처럼 연결하는 것이다. 예를들어 <b> 명령어1 | 명령어2 면</b> "명령어1를 실행 후 그것의 결과를 다시 명령어2의 input로 생각해 명령어2를 실행하고 결과를 나에게 보여주세요" 정도의 의미라고 생각하면 되겠다.

간단한 예제를 들어보자:

<pre>
  <code> $ ls -la | grep gro </code>
</pre>

를 실행하면, gro 가 포함된 파일 또는 폴더를 자세하게 리스트로 출력하시오. 의 의미정도가 되겠다. 참고로 -la는 l (long format) 과 a (all) 의 합성 코맨드가 되겠다 (즉 la 나 al 다 똑같음).

그러면 gro 가 포함된 모든 파일의 긴 리스트가 나온다.

<h1> grep options </h1>

Grep 명령어를 실행할 때 다음과 같은 옵션을 고려할 수 있다.

<ul>
  <li> -i : case insentitive </li>
  <li> -c : number of matches </li>
  <li> -n : line number 까지 출력 </li>
  <li> -v : match 안된 것 까지 다 출력 </li>
</ul>

<h1> sort </h1>

결과물의 리스트를 정렬할 수 있다. 다음과 같은 option을 사용할 수 있다:

<ul>
  <li> -r : reversed sort </li>
  <li> -n : numerical sort </li>
  <li> -f : upper and lowercase sort </li>
</ul>

이 외에도 너무나 많다. 아주 기본적인 내용만 담았고 더 자세하게 알려면 구글에서 documentation을 살펴보시길.
