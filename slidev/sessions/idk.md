---
theme: dracula
---
# effective control

how to make motors and mechanisms do exactly what you what them to do

---

# drum shooter example

<div class="flex flex-row space-x-24">
<div class="w-120">

take a look at [this robot reveal](https://www.youtube.com/watch?v=1rzbSWugDUQ) and see how quickly they shoot. that takes a lot of energy, slowing down the shooter. shots are more accurate if the shooter stays at the same speed the entire time; how do we accomplish that?

</div>

<img
src="https://www.chiefdelphi.com/uploads/default/optimized/4X/a/3/8/a381d4698fcc264f7bf9b9dca2f7fb35d2751692_2_690x460.jpeg"
alt="2910's 2026 robot, REBLITZ"
/>
</div>

---

# BangBang

<div class="flex space-x-12">

<div class="block w-124">

is the speed pretty close to what it's supposed to be?
- if no, turn the motor all the way on
- if yes, turn the motor all the way off
</div>

<img
    src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fimage1.slideserve.com%2F1786222%2Fbang-bang-control-in-action-l.jpg&f=1&nofb=1&ipt=f487902c4d938ae023c26bf164ee8e21ac8c1822f99e408bc573f1ff80e3624c"
    alt="bangbang control graph"
    />
</div>

---

<div class="flex justify-center">
<img
src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fimage1.slideserve.com%2F2980221%2Fpid-controller1-l.jpg&f=1&nofb=1&ipt=2c354dd6e52ea19c36257ae60721bc6a7f78cab8169766a2767e54d866da7002"
alt="PID explainer image"
class="w-160"
/></div>


---

# FeedForward

don't fear this math!

$u = k_s \operatorname{sgn}(v) + k_g + k_v v + k_a a$

$k_s, k_g, k_v, k_a$: 
- values that you set based on testing and/or tuning
- $k_s$ - volts to move the mechanism at all (overcoming static friction)
- $k_g$ - volts to hold position (fighting gravity)
- $k_v$ - volts to keep speed constant at 1 unit
- $k_a$ - volts to keep acceleration constant at 1 unit

$sgn(v)$: if v is positive, then $1$. if v is negative, then $-1$
$v, a$: velocity, acceleration


