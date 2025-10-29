---
title: "[3D-Printed Pillow] Project Rewind: Team Airus & Our 2024 AI-Modeled Pillow Venture"
layout: single
excerpt_separator: "<!--more-->"
# last_modified_at: YYYY-MM-DDTHH:MM:SS+09:00
categories:
  - Start-up
tags:
  - LiDAR Scanning/Photogrammetry
  - 3D Modeling
  - 3D Gaussian Splatting
  - 3D Printing
  - Team Airus (Start-up)
---

<!-- Key tech: 스마트폰 스캔·AI모델링·3D프린팅 -->

I want to share a case study of my most recent and intensive startup experience.
This project was run by "Team Airus," and it was our 9-month journey from November 2023 to August 2024.

Our product was a **3D-Printed Custom-fit Pillow**. 

<!--more-->

Unlike a simple concept, this was a full-throttle effort. 
We assembled a dedicated team of fellow SNU Ph.D. candidates and a pharmaceutical specialist, built a functional MVP, drafted extensive patents, and pitched to numerous Korean accelerator programs.

This 9-month sprint was a practical, real-world education in hardware, market validation, and the critical gap between a novel technology and a viable business.

---

### The Problem: A "Broken" Pillow Market
Our research began with a clear pain point: a significant portion of the population suffers from musculoskeletal issues, and many turn to pillows for relief. However, the market was split between two flawed options:

1. Mass-Market "Functional" Pillows: These are "one-size-fits-all" products. Our research and surveys showed this approach often fails, as a pillow that doesn't fit an individual's unique cervical curve (C-curve) can worsen neck stiffness, shoulder pain, and headaches.

2. "True" Custom Pillows: These high-end products involve manual measurements and custom fabrication. While effective, they are inconvenient (requiring in-person visits), slow to produce, and prohibitively expensive, often costing over 550,000 KRW (approx. $450+).

We aimed to solve the "trilemma" of **3C: Customization, Convenience, and Cost**.

<div style="display: flex; flex-wrap: wrap; justify-content: space-around; gap: 10px;">
  <div style="flex-basis: 49%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-market.png"| relative_url }}" alt="pillow-market" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">Market segmentation & opportunity landscape</p>
  </div>
  <div style="flex-basis: 49%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-problem.png"| relative_url }}" alt="pillow-problem" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">The core problem: the 3C trilemma</p>
  </div>
</div>
  <!-- <div style="flex-basis: 48%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-problem.png"| relative_url }}" alt="Exhibition Poster 1" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">ASDF.</p>
  </div>
</div> -->

---

### Our Solution: A 3-Step "Scan-to-Pillow" Pipeline
<div style="display: flex; flex-wrap: wrap; justify-content: space-around; gap: 10px;">
  <div style="flex-basis: 49%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-solution.png"| relative_url }}" alt="pillow-solution" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">Solution: 3-step pipeline</p>
  </div>
  <div style="flex-basis: 49%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-variants.png"| relative_url }}" alt="pillow-variants" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">Custom pillow variants for each target</p>
  </div>
</div>

Our solution was a 3-step pipeline designed for scalable mass customization :

- Step 1: Convenient 3D Scan Ditch the measuring tape. Users would take a 1-minute 3D scan of their head, neck, and shoulders using their own smartphone's sensors (like LiDAR or TrueDepth). We validated this by comparing high-end scanner data to simple iPhone scans.

<!-- [IMAGE SLOT 1: 3D scan pcd & Mesh file Ground Truth]
Caption: A high-fidelity "ground truth" 3D scan of a user's head and neck, captured with an expensive hand-held scanner. -->

<div style="display: flex; flex-wrap: wrap; justify-content: space-around; gap: 10px;">
  <div style="flex: 1; text-align: center;">
    <video style="max-width: 100%; height: auto;"
          src="{{ "/assets/images/Airus/Custom-fit-Pillow/lidar-pcd.mp4" | relative_url }}" 
          autoplay loop muted playsinline>
      Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #555; font-size: 0.9em;">PCD captured with just an iPhone's LiDAR sensor</p>
  </div>
  <div style="flex: 1; text-align: center;">
    <video style="max-width: 100%; height: auto;"
          src="{{ "/assets/images/Airus/Custom-fit-Pillow/lidar-mesh-poisson-colored.mp4" | relative_url }}" 
          autoplay loop muted playsinline>
      Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #555; font-size: 0.9em;">Colored mesh constructed by the PCD</p>
  <!-- <p style="font-style: italic; color: #555; font-size: 0.9em;">A Neural rendering of a user's scanned head.</p>
  <p style="font-style: italic; color: #555; font-size: 0.9em;">The user's scan captured with just an iPhone's LiDAR sensor</p> -->
  </div>
</div>
<!-- [IMAGE SLOT 2: 3D scan pcd file iphone]
Caption: The same user's scan captured with just an iPhone's LiDAR sensor. The data was comparable, proving our core assumption of convenience was feasible. -->

- Step 2: Automated AI Modeling This was our core IP. The 3D scan data would be fed into our AI, which automatically generated a 3D pillow model perfectly complementary to the user's anatomy. This automated the costly manual design process. We also developed marketing assets using 3D Gaussian Splatting to show customers their digital models in a "high-tech" way.

<div style="display: flex; justify-content: space-around; gap: 1rem;">
  <div style="flex: 1; text-align: center;">
    <video style="max-width: 100%; height: auto;"
    src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-3D-Mesh.mp4" | relative_url }}" 
    autoplay loop muted playsinline>
    Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #555; font-size: 0.9em;">A 3D-printable blueprint of the custom-fit pillow</p>
  </div>
  <div style="flex: 1; text-align: center;">
    <video style="max-width: 100%; height: auto;"
    src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-3D-deformed.mp4" | relative_url }}"
    autoplay loop muted playsinline>
    Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #555; font-size: 0.9em;">A mesh for the non-3D-printed custom pillow variant</p>
  </div>
</div>
<!--  final output of our AI modeling, a 3D-printable mesh (blueprint) of the custom-fit pillow, perfectly contoured to the user's scan. -->

<div style="text-align: center;">
  <video style="max-width: 100%; height: auto;"
        src="{{ "/assets/images/Airus/Custom-fit-Pillow/3dgs-sample.mp4" | relative_url }}" 
        autoplay loop muted playsinline>
    Your browser does not support the video tag.
  </video>
  <p style="font-style: italic; color: #555; font-size: 0.9em;">A Neural rendering of the scanned head (3DGS)</p>
</div>
<!-- A NeRF rendering of a user's scanned head. We planned to use this as a marketing tool to boost customer engagement and build trust in our technology. -->

- Step 3: Cost-Down Manufacturing. The final model would be produced using 3D printing or, as a backup, automated CNC cutting of memory foam.
Below are our actual MVP prototypes, both the 3D-printed version (left) and the custom-cut memory foam version (right).

<div style="display: flex; flex-wrap: wrap; justify-content: space-around; gap: 10px;">
  <div style="flex-basis: 32%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-poc-3D-printed.png"| relative_url }}" alt="pillow-solution" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">PoC: 3D-printed custom pillow</p>
  </div>
  <div style="flex-basis: 66%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-poc-memory-foam.png"| relative_url }}" alt="pillow-variants" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">PoC: Automated CNC cutting of memory foam</p>
  </div>
</div>
<!-- Caption: Our actual MVP prototypes—both the 3D-printed version (left) and the custom-cut memory foam version (right). -->

---

### The Experiment: What We Actually Built
This project went far beyond a pitch deck.

- Assembled the Team: I (AI & Software) partnered with another Ph.D. candidate from SNU's Mechanical Engineering department (an expert in 3D printing and CAD) . Our R&D was backed by deep academic research.

<div style="display: flex; flex-wrap: wrap; justify-content: space-around; gap: 10px;">
  <div style="flex-basis: 50%; min-width: 150px;">
    <img src="{{ "/assets/images/Airus/Custom-fit-Pillow/pillow-thesis.png"| relative_url }}" alt="pillow-thesis" style="width: 100%;">
    <p style="font-style: italic; color: #555; font-size: 0.9em;">My co-founder's master's thesis on ergonomic custom-fit pillow design</p>
  </div>
</div>

`이창민. Design and manufacture of custom-fit pillow in perspective of cervical spine pose maintenance. 2019. PhD Thesis. 서울대학교 대학원.`

- Built the MVP: As shown above, we successfully built and tested the full pipeline, from scanning ourselves to sleeping on the prototypes.

- Market Validation: We conducted customer surveys on pain points (66 respondents) and Willingness-to-Pay (47 respondents).

- Pitched Extensively: We developed a full business plan (the source of this data ), IR decks, and applied to numerous government grants and private accelerators in Korea.

---

### The Scale-Up Vision (And the Hard Stop)
Our long-term strategy was to start with B2C online sales, expand to B2B consignment in places like aesthetic shops and gyms , and ultimately pivot to a B2B software solution, licensing our core AI-modeling technology to incumbent giants like Nike or Ceragem.

---

### So, what happened? 
The project concluded in August 2024 because we consistently failed to gain traction with investors and accelerator programs.

This forced a blunt "item retrospective." Here’s what I learned:

1. Cool Tech vs. Real Market: We had a strong, defensible technology. But we learned (the hard way) that the Korean functional pillow market is a "Red Ocean." It's a low-barrier, saturated market full of gimmicks and low consumer trust. Our tech was an impressive solution to a problem that, from a business perspective, wasn't big or urgent enough.

2. Market-First, Product-Second: I analyzed other successful startups (like the sleep drink "COZA") and realized they had found a massive, high-growth market (insomnia) and applied a simple product. We had done the opposite: we'd applied a complex, expensive-to-scale product to a small, stagnant, and skeptical market.

3. The Pivot Came Too Late: Our true value was the AI-driven 3D modeling software. But by wrapping it in a pillow, we burdened ourselves with the challenges of hardware, manufacturing, and a saturated market. Our pitch was muddled. We should have led with the B2B software vision from day one.

This 9-month sprint was a real-world Ph.D. in product management. It taught me that while my AI skills can build the product, it's the market that determines if you can build a business. This experience was invaluable and has fundamentally shaped how I evaluate new ideas.