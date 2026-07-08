---
title: "How to Point Your .co.ke Domain to Your Hosting (Simple Guide for Kenyan Website Owners)"
author: Philip
category: Guides
date: July 8, 2025
readTime: 7 min read
excerpt: A simple, step-by-step guide for Kenyan website owners on how to point your .co.ke domain to your hosting provider. Covers Truehost, HostPinnacle, Novahost, and more.
image_color: linear-gradient(135deg,#f093fb,#f5576c)
featured: true
tags: Domain, DNS, Kenya, Truehost, HostPinnacle, Novahost, Beginner Guide
---

You have just done something exciting. You bought a domain name, maybe something like yourbusiness.co.ke, and you also bought hosting from a Kenyan hosting company. You are ready to see your website live.

Then you type your domain into the browser and nothing shows up. Or worse, you see a strange default page that has nothing to do with your business. You start to panic. Did you lose your money? Did something go wrong?

Relax. This happens to almost everyone the first time, and it has a very simple fix. The problem is usually that your domain has not been pointed to your hosting yet. In this guide, we will explain what that means in plain language and walk you through exactly how to do it, whether your hosting is with Truehost, HostPinnacle, Novahost, or any other Kenyan provider.

## Why Your Domain and Hosting Are Two Different Things

Many new website owners assume that buying a domain and buying hosting is the same purchase. It is not.

Think of your domain name as your business address, like a plot number. Your hosting is the actual building sitting on that plot, where all your website files, images, and content live. Buying the address does not automatically build the house on it. You need to tell the address system where the house is located. That is what pointing your domain to hosting means.

The tool that connects the two is called a nameserver. A nameserver is simply a set of instructions that tells the internet "when someone types this domain, send them to this hosting company's servers." Without the correct nameservers, your domain has no idea where your website actually lives, so nothing shows up.

## What You Need Before You Start

Before you begin, make sure you have these two things ready.

First, you need access to the account where you bought your domain. This could be KeNIC directly, or an agent like Truehost, HostPinnacle, Kenya Web Experts, Sasahost, or any other registrar.

Second, you need the nameserver details from your hosting company. These are usually sent to you by email right after you buy hosting, and they also appear in your hosting client area or welcome message.

If you bought your domain and your hosting from the same company, this whole process is usually already done for you. This guide is mainly for people who bought their domain from one company and their hosting from another, which is very common in Kenya.

## Step 1: Find Your Hosting Nameservers

Every hosting company gives you a set of nameservers that look something like this:

ns1.hostingcompany.com
ns2.hostingcompany.com

Here is where to find them depending on your host.

**Truehost.** Log into your Truehost client area. Go to your active hosting service. The nameservers are listed on that page, usually something like ns1.truehost.co.ke and ns2.truehost.co.ke.

**HostPinnacle.** Log into your HostPinnacle client area and open your hosting package details. You will see nameservers listed there, often something like ns1.hostpinnacle.co.ke and ns2.hostpinnacle.co.ke.

**Novahost.** Log into your Novahost account dashboard. Under your hosting plan, the nameserver details are shown clearly, often in a welcome email as well.

[TIP] Can't Find Your Nameservers? | If you cannot find them anywhere, do not guess. Open a support ticket or send a WhatsApp message to your host and simply ask, "What are the nameservers for my hosting account?" Any hosting company worth your money will answer this in minutes.

## Step 2: Log Into Where You Bought Your Domain

Now go to the account where you registered your domain. This might be a completely different website from your hosting company.

Log in and look for a section called **Domains**, **My Domains**, or **Manage Domains**. Click on your specific domain name, the one you want to point to your hosting.

## Step 3: Change the Nameservers

Inside your domain management page, look for an option called **Nameservers**, **DNS Management**, or **Name Server Settings**.

You will usually see a choice between "Default Nameservers" and "Custom Nameservers." Choose **Custom Nameservers**, then delete whatever is currently listed there and replace it with the nameservers you got from your hosting company in Step 1.

Most hosts give you two nameservers, sometimes three. Enter each one in its own field, save your changes, and you are done with the technical part.

## Step 4: Be Patient With DNS Propagation

Here is the part that catches people off guard. After you save your new nameservers, your website will not appear instantly. This waiting period is called **DNS propagation**, and it is completely normal.

Think of it like informing everyone in a large market that your shop has moved to a new stall. Some people hear the news immediately. Others take a while to get the message. During this time, some visitors might still see your old page or nothing at all, while others already see your new site.

In Kenya, this usually takes between one and twenty four hours. In rare cases it can take up to forty eight hours. There is nothing wrong if your site is not showing after one hour. Give it time before you start worrying.

## Common Problems and How to Fix Them

**"I changed the nameservers but nothing has changed after two days."**
Double check that you typed the nameservers correctly, with no extra spaces or typing mistakes. A single wrong letter will break everything.

**"My website shows a default page from my registrar, not my hosting."**
This usually means the nameserver change has not fully propagated yet, or the nameservers were not saved correctly. Log back in and confirm they are still set correctly.

**"My site works on my phone but not on my laptop, or the other way around."**
This is simply propagation happening at different speeds for different internet providers. It will settle down within a day or two.

**"I am scared to touch these settings in case I break something."**
This is a common and fair worry. The good news is that changing nameservers does not delete anything from your domain or your website files. If you make a mistake, you can always go back and correct the nameservers again. Nothing is permanent here.

## A Quick Story to Put Your Mind at Ease

Picture a small business owner in Nairobi who spent an entire afternoon refreshing her browser, convinced she had lost her money on a domain that "did not work." She had bought her domain from one company and her hosting from another, and nobody had explained that these two pieces needed to be connected manually. Once she found the correct nameservers and updated them, her site was live by the next morning. The domain was never broken. It simply needed to be told where to look.

If this is you right now, you are not doing anything wrong. You are just missing one small technical step that takes less than five minutes once you know where to look.

## Final Checklist

Before you close this page, confirm the following:

- You have copied the exact nameservers from your hosting company, not guessed them.
- You have entered them under Custom Nameservers in your domain account, not left it on default.
- You have saved the changes.
- You are giving it at least twenty four hours before assuming something is wrong.

Once your domain and hosting are properly connected, this is a one time task. You will not need to repeat it unless you change hosting companies in future, which we will cover in another guide on migrating your website safely without losing your email or your files.