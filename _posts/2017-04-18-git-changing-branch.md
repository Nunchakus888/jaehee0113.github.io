---
layout: post
title: "Git - changing branch - as simple as checkout?"
category: general
date: 2017-04-18
comments: true
disqus_identifier: 06b2fd979f810b67
highlights: false
---

지난 번 branch 의 타입에 대해서 알아 봤는데, 사실 실제 협업 환경에서는 그렇게 branch를 옮기는 작업이 쉽지 않다. 예를들어 내가 어떤 branch에 작업하고 있었는데 이 것을 commit 하지 않고 다른 branch로 간다고 상상해 보자, 이 경우 내가 작업 했던 내용이 다른 branch 로 건너가게 된다. 이 경우, 가장 ideal 한 경우는 tracked / untracked (이 부분은 아직까지 알아보지 않았지만, 간단히 얘기해서 Git 이 버젼 관리를 하는 파일이 있을 수 있고 관리 하지 않는 파일이 있을 수 있는데, 나중에 알아보겠지만, .gitignore 파일에 관리 하지 않는 파일을 정의하면 Git은 이 파일들을 관리하지 않게 된다) 둘다 commit을 하던지, 어떻게든 해결하고 다른 branch로 이동하는 것이다. 이 경우 Git 에서는 stash 라는 개념이 있다.

<h1> Stash 란 ? </h1>

어떤 저장장소라고 생각해 보면 좋겠다. 내가 다른 branch 로 가고 싶은데 가기 전에 변경 사항들을 stash라는 저장장소에 넣어 두고 나중에 다시 돌아와서 다시 그 변경 사항들을 적용하는 방법이다. 가끔 엄청 유용할 때가 있다. 그리고 사용법도 기본적으로는 무척 간단하다. 다른 branch 로 옮기기 전:

<pre>
  <code> git stash [stash 이름] </code>
</pre>

그리고 나중에 간단하게

<pre>
  <code> git stash apply </code>
</pre>

를 통해서 다시 적용하면 된다.

일단 Stashing 은 이정도로 해두도록 하자. 만약, 더 자세하게 관심이 있다면, 추후에 나올 Git Advanced Stashing 을 참고해 주시길.
