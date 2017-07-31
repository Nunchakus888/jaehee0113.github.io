---
layout: post
title: "Understanding UNIX User Group file"
category:
date: 2017-05-05
comments: true
disqus_identifier: 30f0e46913d45f8d
highlights: false
---

<pre>
  <code> Unix 기반의 시스템의 설명입니다 </code>
</pre>

<h1> 배경 </h1>

지난에 chmod 명령어를 공부하면서 그룹중에 Group이 있다고 하였고, 그 그룹을 정의하는 파일이 <code> etc/group </code> 이라고 하였다. 이번에 이 파일의 syntax를 살펴보고자 한다.

일단 이 파일을 열어보면 다음과 같은 내용이 있을 것이다.

<code>ec2-user:x:500:</code>

도대체 이 것이 무엇을 의미하는 것일까?

<h1> Syntax </h1>

각 줄에는 다음과 같은 syntax를 따른다:

<pre>
  <code> 그룹이름:비밀번호:GID:유저리스트</code>
</pre>

<ul>
  <li> 그룹이름: 말 그대로 그룹의 이름이다. </li>
  <li> 비밀번호: 그룹 패스워드이다. 만약 비어있으면 패스워드가 필요없다는 의미이다. 그러나 * 또는 x 로 대체되기도 한다. </li>
  <li> GID: 숫자 (numerical) 로 이루어진 그룹의 ID이다. </li>
  <li> 유저리스트: 이 그룹에 속해 있는 유저의 리스트이다. 각 유저는 <b>, (콤마)</b>로 구분된다. </li>
</ul>

그러면 다음을 해석해보자:

<pre>
  <code> cool_users:x:583:jae,pae</code>
</pre>

cool_users 그룹 (ID는 583) 은 비밀번호가 필요없고 현재 jae 와 pae 유저가 속해있다.
