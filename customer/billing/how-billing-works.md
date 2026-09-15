---
title: How billing works
slug: how-billing-works
category: billing
keywords: [billing, polar, subscription, payment, charge, merchant of record]
reviewed: 2026-09-15
---

# How billing works

## Polar takes the money

Payments are handled by **Polar**, our merchant of record. They take the
payment, hold the card details, issue the invoice and handle the tax.

We never see your card number. Shardly stores which plan you bought and
whether the subscription is active — not how you paid for it.

## One subscription, one server

Each subscription buys one server. Two bots on two servers means two
subscriptions, billed separately, cancellable separately.

## What happens when you pay

1. Polar takes the payment and tells us.
2. We record the order.
3. We build the server.

Steps 2 and 3 are separate on purpose, so a slow moment on our side cannot
lose an order that has already been paid for. If the build fails, it retries
on its own, and if it keeps failing our team is told automatically — you do
not have to notice and report it.

## Managing your subscription

**Billing → Manage billing** opens Polar's portal, where you can change your
card, download invoices, and cancel.

It is their portal rather than ours because they hold the payment details.
Rebuilding it inside Shardly would mean handling card data we deliberately do
not touch.

## Renewals

Weekly subscriptions renew every week, monthly every month, from the day you
bought. There is no minimum term and no contract.

## Tax

Worked out at checkout from where you are. Prices on the site exclude it.

## Still stuck?

[Open a billing ticket.](https://shardly.xyz/app/support/new) Say which email
address you paid with if it is not your account address.
