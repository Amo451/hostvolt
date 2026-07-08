---
title: How to Accept M-Pesa Payments on a WordPress Site in Kenya (Daraja API, Step by Step)
excerpt: A plain-English walkthrough for connecting your WooCommerce store to M-Pesa using Safaricom's Daraja API, no developer required.
author: Phil
date: July 8, 2026
readTime: 7 min read
category: Guides
image_color: linear-gradient(135deg,#0f9d58,#38f9d7)
---

That gap between "wants to buy" and "gave up at checkout" is where a lot of Kenyan businesses are quietly losing money. Your customers aren't carrying credit cards. They're carrying a phone with an M-Pesa balance, and they've been trained by every matatu fare, every shop till, every electricity bill to expect one thing at the point of payment, a PIN prompt and a beep. Anything less than that reads as friction.

The good news is that fixing this is not the developer heavy nightmare it sounds like. Safaricom built an official system called the Daraja API specifically so websites can talk directly to M-Pesa, and getting it running on WordPress is far more within reach than most business owners assume. You don't need to write a line of code. If you can install a plugin and copy paste a few credentials, you can have this working before the day is out. Here's exactly how.

## What You Need Before You Start

A few things need to be in place first.

You need a WooCommerce store already running on your WordPress site, since most M-Pesa integrations work through WooCommerce's payment settings. You also need a Paybill number or a Till number registered under your business, not a personal one. And you need SSL installed on your site, meaning your URL loads as https and not http. Safaricom will not send payment confirmations to a site without SSL, full stop.

If any of these are missing, sort them out first. Everything else builds on top of them.

## Step 1: Create Your Daraja Account

Head over to the Safaricom Developer Portal at developer.safaricom.co.ke and create a free account. This is the platform Safaricom built specifically for businesses and developers who want to connect their systems to M-Pesa.

Once you're logged in, go to My Apps and create a new app. Give it a name related to your business, something like "YourBusiness Website Payments." When asked which API product to attach, choose M-Pesa Express, sometimes labeled Lipa Na M-Pesa Online, since this is the one responsible for the STK Push prompt that pops up on a customer's phone during checkout.

After creating the app, Safaricom will hand you a Consumer Key and a Consumer Secret. Save these somewhere safe. They're the credentials that let your website prove to Safaricom that it's really you making the request.

<div class="callout">
  <div class="callout-title">💡 Pro Tip</div>
  <p>Safaricom rolled out Daraja 3.0 late in 2025, and the whole platform now runs on cloud infrastructure rather than the older setup many tutorials online still describe. If you come across a guide referencing an old dashboard layout or outdated endpoint URLs, that's likely why it looks different from what you're seeing.</p>
</div>

## Step 2: Pick a Plugin That Fits Your Store

You have two real options here. You can hire a developer to write custom code against the Daraja API from scratch, which gives you full control but takes longer and costs more. Or you can install a ready made WooCommerce plugin that already speaks Daraja's language, which is the route most small and medium businesses in Kenya take.

There are several solid plugins to choose from:

- **Free, community maintained plugins** built specifically to connect a Paybill or Till number through STK Push at checkout.
- **Paid plugins** offering extras like automatic order status updates, transaction dashboards, and support for multiple mobile money providers beyond just M-Pesa in case you ever expand regionally.

If your business is simple, one product type, one Paybill number, a free plugin will likely cover everything you need. If you're running a bigger store with higher order volumes, it may be worth paying for a plugin with better support and a cleaner admin dashboard, since chasing failed transactions manually gets tiring fast once your sales pick up.

Search the WordPress plugin directory for M-Pesa WooCommerce options, read the reviews, and check when the plugin was last updated. Daraja has changed enough over the years that an abandoned plugin from three years ago may no longer work properly.

## Step 3: Install and Configure the Plugin

Once you've picked a plugin, install it the normal WordPress way, through Plugins, Add New, then Activate. Most M-Pesa plugins will add a new tab under WooCommerce settings, usually under Payments, where you'll paste in the Consumer Key and Consumer Secret from Daraja.

You'll also need to fill in your Paybill or Till number, sometimes called your shortcode, along with a Passkey that Safaricom provides for STK Push transactions. This information ties your Daraja app to your actual M-Pesa business account, so double check every character before saving. A single typo here is the most common reason payments don't go through later.

Most plugins let you customize the message customers see at checkout when they choose M-Pesa as their payment method. Take a minute to write something clear, something like "You'll receive a prompt on your phone, enter your M-Pesa PIN to complete payment," so customers aren't confused when their screen suddenly asks for a PIN.

## Step 4: Test Everything in Sandbox Mode

Before you touch real money, test the whole flow using Safaricom's sandbox environment, which simulates payments without moving actual funds. Place a test order on your site, select M-Pesa at checkout, and confirm the request reaches your phone or the sandbox test number correctly.

A quick heads up, some developers in the Kenyan tech community have reported the official Daraja sandbox being a bit unstable in early 2026. If you run into strange errors while testing, it's not necessarily something you broke. A community built alternative called Pesa Playground exists for offline testing if you keep hitting walls with the official sandbox.

Test more than just the happy path. Try a payment that times out, one where the customer cancels the prompt, and one where the wrong PIN gets entered. Your site should handle all of these gracefully, not just the case where everything goes perfectly.

## Step 5: Go Live

Once testing looks solid, you'll need to request production access. This usually means submitting your callback URL, the address on your site where Safaricom sends payment confirmations, and waiting for Safaricom to review and approve your integration. Approval typically takes anywhere from three to ten business days, and delays almost always come down to two things, a callback URL that isn't reachable or an SSL certificate that isn't properly configured.

Once approved, you'll switch your plugin settings from sandbox mode to live mode, swap in your production credentials, and you're ready to receive real payments.

## One Thing to Keep in Mind After Launch

Getting M-Pesa working isn't a one time task you finish and forget. Daraja access tokens expire every hour and need to refresh automatically, which good plugins handle for you, but it's worth checking your transaction logs occasionally to make sure payments are actually completing and not silently failing somewhere in the callback chain.

Get this right and you remove the single biggest friction point standing between a Kenyan customer and a completed sale. That alone is worth the afternoon it takes to set up.