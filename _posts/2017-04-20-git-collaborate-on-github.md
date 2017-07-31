---
layout: post
title: "Git - Collaborating with others on GitHub"
category: general
date: 2017-04-20
comments: true
disqus_identifier: 73fe96f510e7fcd7
highlights: false
---

나만의 프로젝트만이 아니라 남의 프로젝트에 참여할 경우가 있을 것이다. 예를들어 내가 만든 Jekyll Theme인 Console은 현재 Contributor 가 3명이 있다. 내 프로젝트에 다른 2명이 코드를 고치거나 추가한 셈인데, 이것이 어떻게 이루어 지는지에 대해 설명하도록 하겠다.

<h1> Step 1. Forking </h1>

그렇다. 우리가 알고 있는 포크의 그 fork이다. 하지만 Git에서는 forking이라 하면, 참여하고자 하는 프로젝트를 clone (복제) 하여 나의 GitHub account에 이 복제품을 repository로 만들고자 하는 작업이다. 그러면 이 복제된 repository에서 개발자는 작업을 시작하게 된다. 물론 이 fork 된 repository는 이 repository의 원 repository에 대한 정보를 알고 있다.

<h1> Step 2. Making a pull request </h1>

Pull request는 말 그대로, pull 좀 해달라고 요청 (request) 하는 것이다. 내가 작업한 commit들을 실제 repository에 merge 해야 하는데, 이 경우 실제 주인 허락 없이는 merge를 할 수 없고, commit 대신 pull request를 보내서 실제 repository 의 주인이 허락을 하면 그 commit이 실제 repository에 merge 되는 것이다. 이렇게 다른 사람의 프로젝트에 참여할 수 있다.

보통 <b>Contributing</b> 이라는 제목으로 README.md 에 대부분 어떻게 참여하는지 방법들이 나와있지만, 기본적으로 저 2개의 스텝을 따를 것이다.
