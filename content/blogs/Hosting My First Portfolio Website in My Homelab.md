---
title: "Hosting My First Portfolio Website in My Homelab"
date: 2025-03-13
tags: ["Homelab","Static Website", Kubernetes Deployment]
draft: false
description: "A summary about how I setup my first static website portfolio in my Kubernetes cluster"
---
Today is the day I successfully hosted my own portfolio website in my homelab. I started coding my portfolio around three months ago, and it was very difficult for me since I do not have a background in coding HTML, CSS, and JavaScript.

The first design of this webpage came from a YouTube channel called *How to Web Dev*. The creator coded it live, and I manually copied the code from his video. A lot of work, right? 😄

It was worth it though, because I created the base design that I liked, which I could enhance and add features to. That is exactly what I did with the second page of the website. It took me days of coding, adding features and design elements, and trying to figure out how different parts of the code connected. I was not that good or experienced with JavaScript, but thanks to ChatGPT, I managed to understand the logic and find workarounds to get the output I wanted. In the end, it was fun, though the website still has a lot of work to do.

While I was building the site, I was also planning to create a DevOps system around it. My goal was to build a GitOps workflow in Kubernetes so I could easily update the deployment image and have the changes automatically reflect on the website.

That plan was also successful. I used my old laptop as my Ubuntu Server and installed K3s on it. Deploying the website application in Kubernetes was pretty easy and straightforward since I already had a pre-built Docker image in my Docker Hub account that I could pull. This was also when I gained a better understanding of Kubernetes networking.

For the GitOps part, I used FluxCD, which I was not very familiar with at first. But thanks to my mentor, Mischa Van Den Burg, and the course I took, I finally got a good grasp of the GitOps system and FluxCD. Before this, I was more familiar with ArgoCD since that is what we use at my day job.

Once the system and application were set, my next task was to make the website publicly accessible so I could share it with recruiters. The setup involved using a domain from Cloudflare and hosting the site through Cloudflare Tunnel, which allowed me to make it publicly available without exposing my home network.

This was where I faced a challenge, especially when setting up a pod user. The issue was that every time I tried adding and setting a user, Nginx would throw permission denied errors during initialization. My idea was to ensure that whenever I accessed the application's pod shell, it would start with a non-root user since this is considered a security best practice for publicly accessible applications in Kubernetes.

After days of troubleshooting and debugging, I finally figured it out and fixed it. The solution involved making changes to the Docker image used for my website application and adjusting the volume mounting settings in my `deployment.yaml` file. Finally, everything is now working, and my site is live at **portfolio.blanktorious.com**.

I had so much fun and learned a lot while working on this project. There were so many “aha moments,” especially when it came to Kubernetes.