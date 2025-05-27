---
streaming face or image info research
---


### 1. **Embedded SVG Output**

This is **vector graphic data**, typically containing:

* Path data for contours, shapes (e.g. eyes, lips, head outline)
* Optional fills, strokes, transforms, and style metadata
* One frame = one full SVG file

If you trace and minify frames at **10 FPS**:

* A typical **minified SVG file** with decent detail might be **10–50 KB** per frame
* 10 FPS × 50 KB = **500 KB/sec**, worst case
* With heavy simplification (posterize + low threshold + aggressive SVGO): **5–15 KB/frame** is possible
* Best case: 10 FPS × 10 KB = **100 KB/sec**

### 2. **Facial Landmark Detection Data**

This is **structured numeric data**, often:

* 68 or 468 points (x, y) per frame
* Each coordinate = float (4 bytes), so:

  * 68 points × 2 × 4 bytes = 544 bytes/frame
  * 468 points × 2 × 4 bytes = 3.7 KB/frame
* 10 FPS:

  * 68-point model: **\~5.5 KB/sec**
  * 468-point model: **\~37 KB/sec**

---

### ⚖️ **Comparison Summary**

| Format                     | Data Size (per second @10 FPS) | Pros                                      | Cons                            |
| -------------------------- | ------------------------------ | ----------------------------------------- | ------------------------------- |
| **Minified SVG**           | 100–500 KB                     | Looks good, direct visual format          | Heavy, not semantically compact |
| **Facial landmarks (68)**  | \~5.5 KB                       | Extremely lightweight, precise control    | Needs rendering logic on client |
| **Facial landmarks (468)** | \~37 KB                        | High fidelity (e.g., lipsync, expression) | Still lighter than SVGs by far  |

---

### ✅ **Conclusion**

**Facial landmark detection data is *orders of magnitude* more efficient** than minified SVGs for streaming a speaking face — especially if your goal is real-time tracking, animation, or remote visualization.

If you're building:

* **A renderer/player**: use facial landmarks.
* **Visual archives or standalone assets**: SVG makes sense.


---
cell pricing 05/25:
---


Here’s what you’ll pay for truly unlimited LTE, ranked by lowest-to-highest monthly cost, followed by a few of the best “big but capped” data deals (again sorted by price).

---

**1. Absolute cheapest unlimited LTE**

> *regardless of post-cap speed*

* **US Mobile “Unlimited Flex”** – **\$17.50/mo** when you pay annually (12-month commitment) ([US Mobile][1])

  * Unlimited talk, text & data on three national networks
  * Data deprioritized after a high-speed allotment (the “Flex” plan includes a modest premium-speed bucket before throttling)

* **US Mobile “Unlimited Starter”** – **\$19/mo** (12-month annual plan) ([US Mobile][1])

  * Unlimited talk, text & data; 35 GB of high-speed data before speeds are reduced

* **Mint Mobile Unlimited (new-customer offer)** – **\$15/mo for first 3 months** (prepaid, upfront \$45) ([Mint Mobile][2])

  * Unlimited talk, text & data; up to 35 GB of LTE, then deprioritized

> ⚠️ After the promo ends, Mint reverts to \$30 /mo. If you want a long-term rate, US Mobile at \$17.50–\$19 /mo is the lowest.

---

**2. Cheapest unlimited-after-cap (throttled) plans**

> *flat post-cap speeds, no true “deprioritization”*

* **Boost Mobile Unlimited** – **\$25/mo** (AutoPay)

  * 30 GB at LTE speeds, then 512 kbps thereafter ([Tello.com][3])
* **Visible Basic** – **\$25/mo**

  * Unlimited LTE data (deprioritized), hotspot up to 5 Mbps
* **Tello Unlimited** – **\$25/mo** (intro rate)

  * 35 GB at full LTE, then throttled (5 GB hotspot included) ([Swappa.com][4])

---

**3. High-data (but capped) plans—best GB-per-dollar**

*for heavy users who don’t need “unlimited”*
| Data Allowance | Price (per mo) | Cost per GB | Notes & Source |
|---|---|---|---|
| **20 GB** | \$25 | \$1.25/GB | Mint Mobile 3-mo plan ([Mint Mobile][5]) |
| **15 GB** | \$20 | \$1.33/GB | Mint Mobile 3-mo plan ([Mint Mobile][5]) |
| **10 GB** | \$19 | \$1.90/GB | Tello “Smart” plan ([Tello.com][3]) |
| **5 GB** | \$14 | \$2.80/GB | Tello “Value” plan ([Tello.com][3]) |
| **40 GB** | \$40 | \$1.00/GB | Total Wireless 40 GB add-on ([Total Wireless][6]) |

---

**Bottom line:**

* **If you need unlimited data** at *any* post-cap speed, lock in US Mobile’s annual “Unlimited Flex” at **\$17.50/mo**.
* **If you just need lots of data** (and don’t mind a hard limit), Mint Mobile’s 20 GB for \$25 or Tello’s 10 GB for \$19 are your best per-GB values.

[1]: https://www.usmobile.com/get-started-unlimited?srsltid=AfmBOoqZpuO2pLx_DFo-VlkMJQRRSE1Gcs64eutUuo4NnteBa_L40Xtw&utm_source=chatgpt.com "Unlimited Phone Plans from $23/mo. All-in. Start Instantly. - US Mobile"
[2]: https://www.mintmobile.com/plans/?utm_source=chatgpt.com "Phone Plans with Unlimited Talk, Text, & Data - Mint Mobile"
[3]: https://tello.com/buy/custom_plans?srsltid=AfmBOorRh2ha_1amzDsKywySotkqB9GtoAcaD3lvdQBpv9aByaevsJse&utm_source=chatgpt.com "Build Your Own Plan | Mix Minutes & Data - Tello Mobile"
[4]: https://swappa.com/mobile/tello/plans/tello-unlimited?srsltid=AfmBOorHz7-mx1BIu3jfZo2RfZvKd23LubH46q0gzOhf1AF7wFQ4Y4Y1&utm_source=chatgpt.com "Unlimited Tello Plan - Swappa.com"
[5]: https://www.mintmobile.com/product/03-month-unlimited-sim-card-plan/?utm_source=chatgpt.com "3 Month Plans - Mint Mobile"
[6]: https://www.totalwireless.com/plans/40GB-data-plan?utm_source=chatgpt.com "40GB Data Plan $40 - Total Wireless"




