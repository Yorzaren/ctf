---
title: "CyberForce 2021 - Collect and Operate"
categories:
  - CyberForce
tags:
  - CyberForce
  - CyberForce-2021
  - CyberForce Adventurer
---

# Collect and Operate
One of the categories in the Department of Energy's CyberForce Program - Conquer the Hill: Adventurer Edition 2021

[CyberForce 2021 Writeup](/ctf/cyberforce/cyberforce-2021-adventurer-writeup/)

{% include toc %}

## Collect and Operate: Anomaly 22 (20pts)
The company you are working for has some legal requirements being worked out that could prevent you from collaborating with people in certain countries. Although this isn’t official yet, your department wants to prepare and has tasked you with setting up a test process to identify country codes from IP addresses. 

You have been given a small list of test data. Your job is to identify the IP in the list that has a country code that is outside of the United States. For example, the United States has a country code of “US”, and Japan has a country code of “JP”. 

For this anomaly you should take advantage of whois functions on operating systems like Linux, or geoip or whois libraries for programming languages. 

syntax hint: looking for an IP address: e.g., 12.345.234.233

### Solution

Run the script

```
for ip in $(cat testing-ips.txt); do whois $ip | echo "$ip $(grep 'Country')"; done > whois.txt
```

whois.txt
```
66.249.64.15 Country:        US
17.248.128.5 Country:        US
108.59.80.88 Country:        US
173.245.48.52 Country:        US
17.248.128.12 Country:        US
17.248.192.234 Country:        US
66.249.64.123 Country:        US
157.240.7.8 Country:        US
91.236.122.136 
198.41.128.56 Country:        US
157.240.7.123 Country:        US
157.240.7.56 Country:        US
17.248.192.19 Country:        US
173.245.48.6 Country:        US
108.59.80.27 Country:        US
17.248.128.129 Country:        US
198.41.128.68 Country:        US
173.245.48.25 Country:        US
17.248.192.12 Country:        US
66.249.64.25 Country:        US
108.59.80.240 Country:        US
66.249.64.110 Country:        US
198.41.128.122 Country:        US
108.59.80.29 Country:        US
173.245.48.48 Country:        US
```

The only one that stands out is `91.236.122.136`.

Ans: `91.236.122.136`

## Collect and Operate: Anomaly 47 (20pts)
After you construct your two layer model, which two tactics weren’t used by APT19 and APT33 according to MITRE? 

Syntax hint: Answer in alphabetical order with selections separated by comma with no space in between. e.g., apples,oranges

### Solution

After making the model it wasn't clear cut but you can eliminate things using a bit of logic to get the answer.

Ans: `Collection,impact`

## Collect and Operate: Anomaly 48 (20pts)
Based on results from the ATT&CK mapping, which technique was executed under tactics of Lateral Movement and Command & Control?

syntax hint: answer is not case sensitive, place spaces in between words

### Solution

Ans: `Remote File Copy`

## Collect and Operate: Anomaly 49 (20pts)
Based on results from the ATT&CK mapping, if you were to investigate the tactic of Lateral Movement, confirm the most commonly leveraged technique. However to answer the question, what is the recommended mitigation by MITRE for this technique?

syntax hint: answer is not case sensitive, include spaces in between words

## Collect and Operate: Anomaly 50 (20pts)
Your IR team has just received a Cyber bulletin from your SOC & ISAC partners regarding threats posed by unmanned aircraft systems or drones. Confirm where the report speaks to how commercial UAS variations communicate with both ground stations and operators. Examine the description of the feeds used and what this allows a malicious actor to perform.

Should data be extracted by a malicious actor, which MITRE ATT&CK technique speaks to exfiltration of data over a radio frequency (RF) channel (or Wi-Fi) where the traffic is not routed through the same enterprise network?

syntax hint: answer is not case sensitive, include spaces in between words

### Solution

Ans: `Exfiltration Over Other Network Medium`

## Collect and Operate: Anomaly 81 (20pts)
What is the name of the federal law which first prohibited accessing a computer without authorization, and when was it enacted? 

Syntax hint: 1900 Argonne Act

### Solution

Ans: `1986 Computer Fraud and Abuse Act`

## Collect and Operate: Anomaly 82 (20pts)
What is the name of the family of ransomeware that was used in a series of powerful global cyberattacks in 2017?

Syntax hint: answer is not case sensitive, no spaces, include slash in your answer:
e.g., apples/bananas

### Solution

Note: It was marked wrong for most of the competition but I'm guessing someone checked into it because I ended up getting the points for it after all.

Ans: `WCry/WannaCry`

## Collect and Operate: Anomaly 85 (20pts)
What is the name of a network site that appears to have valuable information but is in fact isolated and monitored is what kind of security measure?

Syntax hint: answer is not case sensitive, no spaces

### Solution

Ans: `Honeypot`

## Collect and Operate: Anomaly 92 (20pts)
What is the name of the recent attack developed that exploits dynamic random-access memory to expose the contents of memory that is physically located near the originating address?

Syntax hint: answer is not case sensitive, no spaces

### Solution

Ans: `Rowhammer`

## Collect and Operate: Anomaly 83 (25pts)
What names were given to the two related microprocessor vulnerabilities that were the first made public at the start of 2018

Syntax hint: answer is not case sensitive, include the word "and" in your answer.
e.g., Pineapple and apple

Please answer this in reverse alphabetic order, e.g., pineapple and apple

### Solution

Ans: `Spectre and Meltdown`

## Collect and Operate: Anomaly 86 (25pts)
List the 3 parts of the CIA triad

syntax hint: e.g, Apples, Bananas, Oranges

### Solution

Funny enough I alphabetized it because the example syntax was alphabetical so I was marked wrong and had to talk to support. They didn't anticipate people doing that. Oops.

Ans: `Availability, Confidentiality, Integrity`

## Collect and Operate: Anomaly 88 (25pts)
What are the properties of a secure cipher as identified by Claude Shannon? These properties, when present, work to thwart the application of statistics and other methods of cryptanalysis.

Syntax hint: Answer this anomaly in alphabetic order, include the word "and".
e.g.
Apples and bananas, not bananas and apples

### Solution

Ans: `Confusion and diffusion`

## Collect and Operate: Anomaly 89 (30pts)
Decrypt the following Vignere cipher with a key of "DOECDC": Fcriucwipcwkrb, e ylpqsv kv ari!

Syntax hint: answer is not case sensitive, include comma(s) and exclamation point

### Solution

Used: https://cryptii.com/pipes/vigenere-cipher

and just plugged in the ket and ciphertext.

Ans: `Congratulation, a winner is you!`

## Collect and Operate: Anomaly 2 (50pts)
Suppose vectors v1 and v2 are elements of the basis Bv = {v1,v2} and that u1 and u2 are elements of the basis Bu = {u1,u2}. Find the change of basis matrix from Bv to Bu. Answer in the following format:

a11,a12,a21,a22 (where axy represents the entry in the xth row and yth column).

If an entry is a fraction, simplify fully and use an x/y format. 

## Collect and Operate: Anomaly 51 (50pts)
Based on the log data output and the pattern of activity associated with it: 
A) which technique from the MITRE ATT&CK framework is used? 
B) Based on the pattern of activity associated with the events, which object is being created? 

Format asnwer as "A","B"
e.g., 
"apples bananas orange", "grapes"

## Collect and Operate: Anomaly 79 (50pts)
What is the BINARY output of a bitwise XOR operation between the HEX numbers f47 and 98a?

syntax hint: only include numbers in your answer

### Solution

Used: http://xor.pw/#

Don't forget to set the output as binary and the inputs as hexadecimal 

Ans: `11011001101`

## Collect and Operate: Anomaly 3 (100pts)
You have intercepted an output file from a program written in C that asks for a key to display a message. You have no access to the key, so you investigate how you can use the output file you have to find the secret message yourself 

Syntax hint: answer should be in the following format: _apples_bananas_apples_oranges

### Solution

I downloaded snowman and ran it on the program to get:

```

int64_t __gmon_start__ = 0;

void _init() {
    int64_t rax1;

    rax1 = __gmon_start__;
    if (rax1) {
        rax1();
    }
    return;
}

int64_t __cxa_finalize = 0;

void fun_1060(int64_t rdi) {
    goto __cxa_finalize;
}

int64_t printf = 0x1046;

void fun_1040(int64_t rdi, void* rsi) {
    goto printf;
}

int64_t _ITM_deregisterTMCloneTable = 0;

int64_t deregister_tm_clones(int64_t rdi) {
    int64_t rax2;

    rax2 = 0x4040;
    if (1 || (rax2 = _ITM_deregisterTMCloneTable, rax2 == 0)) {
        return rax2;
    } else {
        goto rax2;
    }
}

int64_t putchar = 0x1036;

void fun_1030(int64_t rdi, void* rsi) {
    goto putchar;
}

int64_t __isoc99_scanf = 0x1056;

void fun_1050(int64_t rdi, void* rsi) {
    goto __isoc99_scanf;
}

int64_t __libc_start_main = 0;

int64_t main();

void __libc_csu_init(int32_t edi, int64_t rsi, int64_t rdx);

void __libc_csu_fini();

void _start() {
    void* rsp1;
    int64_t rdx2;
    int64_t rax3;

    rsp1 = reinterpret_cast<void*>(reinterpret_cast<int64_t>(__zero_stack_offset()) + 8);
    __libc_start_main(main, __return_address(), rsp1, __libc_csu_init, __libc_csu_fini, rdx2, (reinterpret_cast<uint64_t>(rsp1) & 0xfffffffffffffff0) - 8 - 8, rax3);
    __asm__("hlt ");
}

void _fini() {
    return;
}

void fun_1102() {
    return;
}

void __libc_csu_fini() {
    return;
}

int64_t g4010 = 0;

void fun_1036() {
    goto g4010;
}

int64_t _ITM_registerTMCloneTable = 0;

void fun_10c9() {
    int64_t rax1;

    if (1) 
        goto 0x1108;
    rax1 = _ITM_registerTMCloneTable;
    if (!rax1) 
        goto 0x1108;
    goto rax1;
}

signed char __TMC_END__ = 0;

int64_t __dso_handle = 0x4038;

int64_t __do_global_dtors_aux() {
    int1_t zf1;
    int64_t rax2;
    int1_t zf3;
    int64_t rdi4;
    int64_t rax5;

    zf1 = __TMC_END__ == 0;
    if (!zf1) {
        return rax2;
    } else {
        zf3 = __cxa_finalize == 0;
        if (!zf3) {
            rdi4 = __dso_handle;
            fun_1060(rdi4);
        }
        rax5 = deregister_tm_clones(rdi4);
        __TMC_END__ = 1;
        return rax5;
    }
}

void fun_1046() {
    goto 0x1020;
}

void __libc_csu_init(int32_t edi, int64_t rsi, int64_t rdx) {
    int64_t r14_4;
    int64_t r13_5;
    int32_t r12d6;
    int64_t rbx7;
    int64_t rdi8;

    r14_4 = rdx;
    r13_5 = rsi;
    r12d6 = edi;
    _init();
    if (!0) {
        *reinterpret_cast<int32_t*>(&rbx7) = 0;
        *reinterpret_cast<int32_t*>(reinterpret_cast<int64_t>(&rbx7) + 4) = 0;
        do {
            *reinterpret_cast<int32_t*>(&rdi8) = r12d6;
            *reinterpret_cast<int32_t*>(reinterpret_cast<int64_t>(&rdi8) + 4) = 0;
            *reinterpret_cast<int64_t*>(0x3de8 + rbx7 * 8)(rdi8, r13_5, r14_4);
            ++rbx7;
        } while (1 != rbx7);
    }
    return;
}

void frame_dummy() {
    goto 0x10d0;
}

void fun_1056() {
    goto 0x1020;
}

int64_t main() {
    void* rsi1;
    void* rsi2;
    int32_t v3;

    fun_1040("\nEnter in the proper key to display the secret message: ", rsi1);
    rsi2 = reinterpret_cast<void*>(reinterpret_cast<int64_t>(__zero_stack_offset()) - 8 - 8);
    fun_1050("%d", rsi2);
    if (0x66acb != v3) {
        fun_1040("\nYou have been denied access to the key", rsi2);
    } else {
        fun_1040("\nYour answer is this: python nested for loops", rsi2);
    }
    fun_1030(10, rsi2);
    return 1;
}
```

And read the `Your answer is this: python nested for loops` line and added back the underscores.


I could have also done strings on it and read the answer but I wasn't sure that was correct because it was too easy. 

Decompiling the program made me feel like I was sure I had the answer (which was correct).

```
Enter in the proper key to display the secret message: 
Your answer is this: python nested for loops
You have been denied access to the key
```

Ans: `_python_nested_for_loops`

## Collect and Operate: Anomaly 23 (100pts)
From: sgoodman@flyinglotus.com
Sent: Saturday, November 14, 2020 1:00 PM
To: cyberops@flyinglotus.com
Subject: Breach Investigation

Received word that some of our employee’s email addresses were included in a recent email dump. I’ve attached the sqlite database that has been making the rounds. When you get a chance, can you determine the unique amount of our employee’s emails are included in this dump? Once we have that number, we can determine next steps. 

Thanks

syntax hint: numerical answer

## Collect and Operate: Anomaly 45 (100pts)
A host on the corporate ITnetwork has beencompromised and is using DNS to phone home. This activity has been noticed and the DNS logs have been dumped. Analyze the DNS logs and identify what information has been transferred.

syntax hint: answer is not case sensitive, no spaces