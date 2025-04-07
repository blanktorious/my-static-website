---
title: "Started my Homelab"
date: 2025-03-10
tags: ["Homelab", "K3s", "Linux"]
description: "The story of what was my experience starting my Homelab"
draft: false
---
Today is March 10, 2025, and I am writing this at 4:30 in the morning. I cannot sleep, so I just wanted to write down my thoughts about the difficulties I have faced or am currently facing while setting up my homelab.

I started “homelabing” on February 26, beginning with a simple Ubuntu Server installation on my old laptop which is a Dell Latitude 7290. I set up SSH and then successfully assigned it a static IP. That alone was a challenge for me. It took me about 10 hours just to get the static IP working, which pretty much confirms that networking is not my strong suit but that is the whole point why I started homelab. That is to have an environment where I can play and learn about the things I am not experienced at.

After that, I installed K3s. The installation itself was smooth, and I had no issues. I managed to make the cluster accessible locally, so I did not have to SSH into the server every time I wanted to run kubectl commands. What I did was add the K3s cluster context to my local machine, which was a bit of an aha moment for me. At my day job, when I add a Kubernetes cluster from Azure, I just copy and paste the commands. But doing it manually made me really understand how merging contexts actually works.

Once that was set up, my next goal was to host a portfolio website I built months ago. I wanted to replicate the architecture my current company uses, meaning GitOps, a private container registry, a load balancer, and all that good stuff.

Long story short, I successfully deployed the application and accessed it using port forwarding. After that, I set up Traefik as an ingress controller and was able to reach the site via the server’s IP. The next step was to make it publicly accessible since I had already bought a domain through Cloudflare. But that is where I hit a roadblock because I just could not get it to work.

After a lot of research, I realized that my K3s setup was not as secure as it should be. Hosting an application this early without a solid infrastructure in place is not really ideal.

For now, my main focus is on the infrastructure itself. I want to build a strong foundation where I can play around and experiment without worrying too much about security risks or stability issues. My next steps will be to properly implement GitOps, set up my own container registry using Harbor, and make sure everything is more structured before I try hosting anything publicly again.

That is all for now. See you in the next blog!