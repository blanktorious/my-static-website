---
title: "Self Hosting Container Registry"
date: 2025-04-05
tags: [Homelab,Container Registry,Kubernetes,Harbor]
draft: false
description: "My thought process on why want to self host a container registry"
---
This blog is to just share what is my thought process on why I wanted to build Harbor my self hosted container registry.

My portfolio website is deployed using an image pushed to my account in docker hub. For it to be pulled by my GitOps system I had to make the image publicly accessible. This is obviously insecure and someone can just use that image. So, I decided to self host a container registry.

In my day job we use Azure Container Registry and that gave me the understanding of what is its purpose. I wanted to build something like that in my homelab. My initial idea was just to use the registry image by docker to understand how can I setup a self hosted container registry then after that I’ll proceed on upgrading to harbor. I’ve shared this in the Kubecraft community and Mischa recommended to just go straight up to Harbor.

After some research, it is actually better to just go with harbor since it has more features that I can play with. Also, my plan was to build a CI/CD github action to automatically deploy my blogging website that I will build using Hugo. So, it’s better to go with harbor since it has user permission feature which will help me secure the authentication to my github actions.