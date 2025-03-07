---
pageLayout: home
externalLinkIcon: false
config:
  -
    type: hero
    full: true
    background: '#FFFFFF'
    hero:
      name:
      tagline:  Web 3.0 &<br>Post-Quantum Security
      text: Dedicated to exploring all possibilities of Web 3.0
      actions:
        -
          theme: brand
          text: Research
          link: /research/
        -
          theme: alt
          text: Github →
          link: https://github.com/pengzhanbo/vuepress-theme-plume
  -
    type: custom
---
<script setup>
import Swiper from 'vuepress-theme-plume/features/Swiper.vue'
</script>
<h1 style="text-align: center;font-weight: bold;margin-bottom: 20px;">Welcome to the Web 3.0 & Post-Quantum Security Laboratory</h1>
<div style="width: 800px; margin: 0 auto;margin-bottom: 20px;">
Web 3.0 represents the next evolution of the internet, emphasizing decentralization, blockchain technology, and enhanced user control over data. While it offers promising advancements in transparency and autonomy, it also introduces new security challenges. Decentralized applications (dApps) and smart contracts, fundamental components of Web 3.0, are susceptible to vulnerabilities such as coding errors, reentrancy attacks, and logic flaws. These weaknesses can be exploited by malicious actors to manipulate transactions or siphon off digital assets, as evidenced by various high-profile breaches in decentralized finance (DeFi) platforms. Ensuring security in Web 3.0 requires rigorous code audits, formal verification of smart contracts, and the implementation of robust cryptographic protocols designed to safeguard decentralized networks against sophisticated attacks.
<br></br>
<br></br>
Concurrently, the advent of quantum computing poses a significant threat to the cryptographic foundations that underpin much of today's digital security, including blockchain technologies integral to Web 3.0. Quantum computers have the potential to break widely used cryptographic schemes like RSA and ECC through algorithms such as Shor's algorithm, rendering current encryption methods obsolete. Post-quantum security focuses on developing new cryptographic algorithms that are resistant to quantum attacks. Integrating post-quantum cryptographic solutions into Web 3.0 is essential to future-proof decentralized applications and protect against the looming quantum threat, ensuring the longevity and trustworthiness of next-generation internet technologies.
</div>
<div style="width: 600px; height: 400px; margin: 0 auto;margin-bottom: 20px;margin-top: 20px;">
<Swiper :items="['https://theme-plume.vuejs.press/plume.png', 'https://theme-plume.vuejs.press/plume.png']" />
</div>
<div style="width: 800px; margin: 0 auto;margin-bottom: 20px;">
</div>

<h1 style="text-align: center; font-weight: bold;">News</h1>
<SimpleNews />
  <div style="text-align: right;">
        <a href="/PolyU-Web-3.0-and-Post-Quantum-Security-Lab/news/" style="display: inline-flex; align-items: center; padding: 10px 20px; color: #007BFF; text-decoration: none;">
            More 
            <span style="margin-left: 5px;">&gt;&gt;</span>
        </a>
    </div>
<h1 style="text-align: center;font-weight: bold;">Quick Links</h1>
<div style="width: 400px; margin: 0 auto; margin-bottom: 20px; text-align: left;">
    <p>
        <span style="margin-right: 8px;">📍</span>
        <a href="https://www.polyu.edu.hk/comp/" style="text-decoration: none; color: #007BFF;">PolyU COMP department</a>
    </p>
</div>
