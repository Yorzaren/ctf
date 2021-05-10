---
title: "waves over lambda"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - cryptography
---

Problem: We made alot of substitutions to encrypt this. Can you decrypt it? Connect with ```nc 2019shell1.picoctf.com 45185```.

```
-------------------------------------------------------------------------------
ezvlphyx mfpf tx gznp dshl - dpfonfveg_tx_e_zqfp_shkach_knrlrfvvzc
-------------------------------------------------------------------------------
jf jfpf vzy knem kzpf ymhv h onhpyfp zd hv mznp zny zd znp xmtr ytss jf xhj mfp xtvi, hvc ymfv t nvcfpxyzzc dzp ymf dtpxy ytkf jmhy jhx kfhvy ag h xmtr dznvcfptvl tv ymf xfh.  t knxy heivzjsfclf t mhc mhpcsg fgfx yz szzi nr jmfv ymf xfhkfv yzsc kf xmf jhx xtvitvl; dzp dpzk ymf kzkfvy ymhy ymfg phymfp rny kf tvyz ymf azhy ymhv ymhy t ktlmy af xhtc yz lz tv, kg mfhpy jhx, hx ty jfpf, cfhc jtymtv kf, rhpysg jtym dptlmy, rhpysg jtym mzppzp zd ktvc, hvc ymf ymznlmyx zd jmhy jhx gfy afdzpf kf.
```

Solution: I just brute forced it with a Substitution Cipher.

![no-alignment]({{ '/picoCTF-2019/solution-files/waves-over-lambda-solution.png' | absolute_url }})

Flag: ```picoCTF{frequency_is_c_over_lambda_mupgpennod}```