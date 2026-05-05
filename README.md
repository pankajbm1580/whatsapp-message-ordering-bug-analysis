# whatsapp-message-ordering-bug-analysis
Messaging order issue
# WhatsApp Message Ordering Bug Analysis

## 📌 Overview
This repository documents a real-world message ordering issue observed in WhatsApp when a device reconnects after being offline.

## 🧪 Scenario
- Device was offline
- Message A sent at 22:06
- Message B sent at 23:26
- Upon reconnect → Message B appeared before Message A

## ❗ Issue
Messages are displayed out of chronological order and remain incorrect even after restarting the app.

## ✅ Expected Behavior
Messages should be displayed in chronological order based on send timestamp.

## ❌ Actual Behavior
Newer messages appear before older messages.

## 📸 Evidence
See `/evidence/screenshot.png`

## 🧠 Analysis
This appears to be caused by:
- Ordering based on delivery/commit time instead of send time
- Missing post-sync reordering logic

## 🔍 Testing Type
- Exploratory Testing
- Edge Case Testing (Offline → Online sync)

## 📊 Severity
Medium

## 🚀 Key Learning
Distributed systems may prioritize delivery over strict ordering, leading to UI inconsistencies if not handled correctly.
