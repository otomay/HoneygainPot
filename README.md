<h1 align="center">Honeygain Pot</h1>
<h4 align="center">🐝A Bot that claim Honeygain pot every day🍯</h4>
<h4 align="center">Powered by GitHub Actions and Python</h4>
<p align="center">
<img src="https://img.shields.io/github/forks/gorouflex/HoneygainPot?style=flat">
<img src="https://img.shields.io/github/stars/gorouflex/HoneygainPot?style=flat">
<img src="https://img.shields.io/github/contributors/gorouflex/HoneygainPot?style=flat">
<p align="center">
<img alt="CodeQL status" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/codeql.yml/badge.svg">
<img alt="Daily trigger status" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/daily.yml/badge.svg">
<img alt="Manual trigger status" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/manual.yml/badge.svg"> (*)
<p align="center">
  <a href="https://github.com/gorouflex/HoneygainPot/">English 🇺🇸</a>
  •
  <a href="README-vn.md">Tiếng Việt 🇻🇳</a>
<p align="center">
  <a href="Debug.md">Debug</a>     
  •
  <a href="#feature">Feature</a>
  •
  <a href="#usage">Usage</a>     
  •
  <a href="#preview">Preview</a>
  •
  <a href="FAQ.md">FAQ</a>   
 <p align="left">
   
<img src="Img/Logo.png"               
     width="170" 
     height="170"></p>

### [Honeygain](https://r.honeygain.me/BADBO762DE) is a service that allows you to 💵 earn **passive income** by **sharing** your **internet** connection with businesses  for web statistics, price comparison, and other verified business processes

> [!WARNING]
> This script is **not** affiliated with or endorsed by Honeygain. Use it at your **own risk** and responsibility.  
The **author** is **not responsible** for any consequences that may arise from using this script. If Honeygain wants me 
to delete this bot, I'll do it.
  
> [!NOTE]
> - Always update your repo following the orginal repo to get latest update + bug fixes, i will not support anything if your repo is outdated.
> - If you facing with errors when using GitHub Actions, please refer to this [debug section](Debug.md)
> - (*): Do not fork this repo if two of these (not only 1 and CodeQL) GitHub Actions status badge show failing, and wait until 1 of these or two of these show passing then you can fork again
> - 'Daily claim' workflows always run every 14:00 UTC +0, if you want to change it, refer to [this](https://github.com/gorouflex/HoneygainPot#how-to-change-the-schedule-to-fit-with-my-timezone-before-the-pot-is-reset)
> <img src="https://i.imgur.com/htGeFlY.jpg">
  
# Feature 

- Claim Honeygain pot and achievements rewards every day with GitHub Actions 🔥
- Checking your current balance

# Usage 

  1. [Fork this repository](https://github.com/gorouflex/HoneygainPot/fork)
  2. Go to your forked repository
  3. Go to `Settings > Secrets and Variables > Actions`, and click the button `New Repository secret`
  4. For the secret name, use `MAIL_JWD` to set your honeygain mail and `PASS_JWD` for your password
  5. Go to your forked repository and go to the Actions tab and press the button `I understand my workflows, go ahead and enable them`

![GitSettings](https://github.com/gorouflex/HoneygainPot/assets/98001973/d8d33621-5717-488d-9a80-6db395c8ac9d)

## How to change the schedule to fit with my timezone before the pot is reset?

> [!IMPORTANT]
Daily workflows file path (default is 14:00 UTC +0): `.github/workflows/daily.yml`

Well, GitHub uses UTC time (UTC +0) for scheduling workflows, so we should convert it to our timezone.

For example: If I want to set the daily trigger to trigger at 9:00 PM (UTC +7), I have to set it to 2:00 PM or 14:00 (24-hour format) (UTC±0) (2+7=9).

```
name: Daily claim
on:
  schedule:
    - cron: '0 14 * * *' # <- UTC Time, replace 0 14
```
So, if I want the daily trigger to run at 5:00 AM (UTC +7), I have to set it to 10:00 PM (UTC±0) (use 24-hour format):
```
name: Daily claim
on:
  schedule:
    - cron: '0 22 * * *' # UTC Time
```

> [!NOTE]
> GitHub Actions schedules can sometimes be delayed by up to 15 minutes due to high demand, so don’t worry!

# Preview

<p align="center">
  <img src="Img/preview (1).jpeg">
  <img src="Img/preview.jpeg">
</p>

## Thanks to
- [MrLolf](https://github.com/MrLoLf/) for [HoneygainAutoClaim](https://github.com/MrLoLf/HoneygainAutoClaim)
- [rfoal](https://github.com/rfoel/) x [duolingo](https://github.com/rfoel/duolingo) for idea
