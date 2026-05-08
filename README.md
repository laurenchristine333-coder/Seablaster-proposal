# Seablaster-proposal
<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sea Blaster — Social Media Proposal</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap" rel="stylesheet">
<style>
:root {
  --pink: #C8266A;
  --yellow: #F5D800;
  --dark: #060E18;
  --ocean: #0B3D6B;
  --ocean-mid: #0D5490;
  --white: #FAFAF8;
  --sand: #F2EAD8;
}
* { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }
body {
  background: var(--dark);
  color: var(--white);
  font-family: 'DM Sans', sans-serif;
  font-weight: 300;
  overflow-x: hidden;
}

/* ── HERO ── */
.hero {
position: relative;
min-height: 100vh;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
text-align: center;
padding: 48px 24px 120px;
overflow: hidden;
background: linear-gradient(180deg, #02090F 0%, #082035 40%, #0B3D6B 80%, #0D5490 100%);
}

/* animated sun glow */
.hero::before {
content:’’;
position:absolute;
top: -80px; left: 50%;
transform: translateX(-50%);
width: 500px; height: 500px;
border-radius: 50%;
background: radial-gradient(circle, rgba(245,216,0,0.18) 0%, rgba(200,38,106,0.08) 40%, transparent 70%);
animation: pulse 6s ease-in-out infinite;
}

@keyframes pulse { 0%,100%{opacity:0.7;transform:translateX(-50%) scale(1);} 50%{opacity:1;transform:translateX(-50%) scale(1.1);} }

/* ocean shimmer layer */
.ocean-shimmer {
position:absolute;
bottom:0; left:0; right:0;
height: 220px;
background: linear-gradient(180deg, transparent 0%, rgba(13,84,144,0.6) 50%, rgba(11,61,107,0.9) 100%);
overflow: hidden;
}
.ocean-shimmer::after {
content:’’;
position:absolute;
inset:0;
background: repeating-linear-gradient(
90deg,
transparent 0px,
rgba(255,255,255,0.03) 2px,
transparent 4px,
transparent 40px
);
animation: shimmer 8s linear infinite;
}
@keyframes shimmer { from{background-position:0 0;} to{background-position:200px 0;} }

/* LOGO IMAGE */
.logo-img {
width: min(480px, 85vw);
filter: drop-shadow(0 0 40px rgba(200,38,106,0.5)) drop-shadow(0 0 80px rgba(245,216,0,0.2));
animation: fadeDown 1s 0.2s ease both;
position: relative;
z-index: 2;
}

.secondary-logo {
width: min(220px, 55vw);
margin-top: 18px;
opacity: 0.85;
filter: drop-shadow(0 2px 12px rgba(0,0,0,0.6));
animation: fadeDown 1s 0.5s ease both;
position: relative;
z-index: 2;
}

.hero-tagline {
font-family: ‘Playfair Display’, serif;
font-style: italic;
font-size: clamp(1rem, 2.5vw, 1.3rem);
color: rgba(255,255,255,0.55);
margin-top: 22px;
letter-spacing: 0.06em;
animation: fadeUp 1s 0.8s ease both;
position: relative; z-index: 2;
}

.price-badge {
margin-top: 40px;
display: inline-flex;
flex-direction: column;
align-items: center;
background: rgba(255,255,255,0.06);
border: 1px solid rgba(245,216,0,0.3);
border-radius: 20px;
padding: 22px 48px;
animation: fadeUp 1s 1s ease both;
position: relative; z-index: 2;
backdrop-filter: blur(16px);
}
.price-badge .label {
font-size: 0.65rem;
letter-spacing: 0.3em;
text-transform: uppercase;
color: var(–yellow);
margin-bottom: 6px;
}
.price-badge .amount {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(3rem, 8vw, 5rem);
line-height: 1;
background: linear-gradient(135deg, #fff 0%, var(–yellow) 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
background-clip: text;
}
.price-badge .sub {
font-size: 0.75rem;
color: rgba(255,255,255,0.45);
letter-spacing: 0.12em;
margin-top: 4px;
}

/* DOLPHINS */
.dolphin-scene {
position: absolute;
bottom: 0; left: 0; right: 0;
height: 200px;
pointer-events: none;
z-index: 3;
}
.dolphin {
position: absolute;
bottom: 30px;
}
.dolphin svg { display: block; }

.dolphin-1 { animation: swim1 14s ease-in-out infinite; left: -120px; bottom: 50px; }
.dolphin-2 { animation: swim2 18s ease-in-out infinite; left: -160px; bottom: 20px; transform: scaleX(-1); }
.dolphin-3 { animation: swim3 20s ease-in-out infinite 4s; left: -100px; bottom: 70px; }

@keyframes swim1 {
0%   { transform: translateX(0) translateY(0); }
25%  { transform: translateX(calc(50vw + 60px)) translateY(-30px); }
50%  { transform: translateX(calc(100vw + 160px)) translateY(0); }
50.01% { transform: translateX(calc(100vw + 160px)) translateY(0) scaleX(-1); }
75%  { transform: translateX(calc(50vw + 60px)) translateY(-20px) scaleX(-1); }
100% { transform: translateX(0) translateY(0) scaleX(1); }
}
@keyframes swim2 {
0%   { transform: scaleX(-1) translateX(0) translateY(0); }
30%  { transform: scaleX(-1) translateX(calc(40vw)) translateY(-25px); }
60%  { transform: scaleX(-1) translateX(calc(80vw + 100px)) translateY(10px); }
60.01% { transform: scaleX(1) translateX(calc(-80vw - 100px)) translateY(10px); }
80%  { transform: scaleX(1) translateX(calc(-40vw)) translateY(-15px); }
100% { transform: scaleX(-1) translateX(0) translateY(0); }
}
@keyframes swim3 {
0%   { transform: translateX(0) translateY(0); }
20%  { transform: translateX(calc(30vw)) translateY(-40px); }
40%  { transform: translateX(calc(60vw)) translateY(-10px); }
60%  { transform: translateX(calc(100vw + 120px)) translateY(-5px); }
60.01% { transform: translateX(calc(100vw + 120px)) translateY(-5px) scaleX(-1); }
80%  { transform: translateX(calc(50vw)) translateY(-30px) scaleX(-1); }
100% { transform: translateX(0) translateY(0) scaleX(1); }
}

/* arc jump for dolphin 1 */
.dolphin-1 { animation: leap1 14s ease-in-out infinite; }
@keyframes leap1 {
0%   { left: -120px; bottom: 50px; transform: scaleX(1) rotate(0deg); }
10%  { left: 15vw;   bottom: 100px; transform: scaleX(1) rotate(-15deg); }
20%  { left: 35vw;   bottom: 50px; transform: scaleX(1) rotate(10deg); }
30%  { left: 55vw;   bottom: 110px; transform: scaleX(1) rotate(-10deg); }
45%  { left: 80vw;   bottom: 50px; transform: scaleX(1) rotate(5deg); }
50%  { left: 110vw;  bottom: 50px; transform: scaleX(1); }
50.1%{ left: 110vw;  bottom: 50px; transform: scaleX(-1); }
60%  { left: 80vw;   bottom: 100px; transform: scaleX(-1) rotate(-10deg); }
75%  { left: 50vw;   bottom: 60px; transform: scaleX(-1) rotate(8deg); }
90%  { left: 20vw;   bottom: 90px; transform: scaleX(-1) rotate(-12deg); }
100% { left: -120px; bottom: 50px; transform: scaleX(1) rotate(0deg); }
}

@keyframes leap2 {
0%   { left: -180px; bottom: 25px; transform: scaleX(1); }
15%  { left: 20vw;   bottom: 80px; transform: scaleX(1) rotate(-8deg); }
35%  { left: 50vw;   bottom: 30px; transform: scaleX(1) rotate(5deg); }
55%  { left: 85vw;   bottom: 70px; transform: scaleX(1) rotate(-5deg); }
60%  { left: 110vw;  bottom: 25px; }
60.1%{ left: 110vw;  bottom: 25px; transform: scaleX(-1); }
75%  { left: 70vw;   bottom: 65px; transform: scaleX(-1) rotate(-6deg); }
90%  { left: 30vw;   bottom: 35px; transform: scaleX(-1) rotate(4deg); }
100% { left: -180px; bottom: 25px; transform: scaleX(1); }
}
.dolphin-2 { animation: leap2 20s ease-in-out infinite 3s; }

@keyframes leap3 {
0%   { left: -100px; bottom: 70px; transform: scaleX(1); }
20%  { left: 25vw;   bottom: 130px; transform: scaleX(1) rotate(-20deg); }
40%  { left: 55vw;   bottom: 70px; transform: scaleX(1) rotate(12deg); }
55%  { left: 80vw;   bottom: 120px; transform: scaleX(1) rotate(-8deg); }
65%  { left: 110vw;  bottom: 70px; }
65.1%{ left: 110vw;  bottom: 70px; transform: scaleX(-1); }
80%  { left: 60vw;   bottom: 110px; transform: scaleX(-1) rotate(-14deg); }
95%  { left: 20vw;   bottom: 80px; transform: scaleX(-1) rotate(10deg); }
100% { left: -100px; bottom: 70px; transform: scaleX(1); }
}
.dolphin-3 { animation: leap3 17s ease-in-out infinite 7s; }

/* wave SVG bottom of hero */
.wave-bottom { position:absolute; bottom:-1px; left:0; width:100%; z-index:4; }

@keyframes fadeDown { from{opacity:0;transform:translateY(-20px);} to{opacity:1;transform:translateY(0);} }
@keyframes fadeUp   { from{opacity:0;transform:translateY(20px);}  to{opacity:1;transform:translateY(0);} }

/* ── CONTENT ── */
.content {
background: #060E18;
position: relative;
z-index: 5;
padding: 0 0 80px;
}

.section-intro {
text-align: center;
padding: 80px 24px 48px;
max-width: 680px;
margin: 0 auto;
}
.section-intro h2 {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(2.2rem, 6vw, 4rem);
letter-spacing: 0.06em;
color: var(–white);
line-height: 1;
}
.section-intro h2 span { color: var(–yellow); }
.section-intro p {
margin-top: 16px;
color: rgba(255,255,255,0.5);
font-size: 0.95rem;
line-height: 1.7;
}

/* cards grid */
.cards {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
gap: 2px;
max-width: 1100px;
margin: 0 auto;
padding: 0 24px;
}

.card {
background: rgba(255,255,255,0.03);
border: 1px solid rgba(255,255,255,0.07);
border-radius: 2px;
padding: 36px 32px;
position: relative;
overflow: hidden;
transition: background 0.3s, transform 0.3s;
}
.card:hover {
background: rgba(255,255,255,0.06);
transform: translateY(-3px);
}
.card::before {
content: ‘’;
position: absolute;
top: 0; left: 0; right: 0;
height: 2px;
background: linear-gradient(90deg, var(–pink), var(–yellow));
opacity: 0;
transition: opacity 0.3s;
}
.card:hover::before { opacity: 1; }

.card-icon {
font-size: 2rem;
margin-bottom: 16px;
display: block;
}
.card h3 {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 1.4rem;
letter-spacing: 0.08em;
color: var(–yellow);
margin-bottom: 10px;
}
.card p {
font-size: 0.88rem;
color: rgba(255,255,255,0.5);
line-height: 1.7;
}

/* platforms strip */
.platforms {
display: flex;
justify-content: center;
gap: 32px;
padding: 60px 24px;
flex-wrap: wrap;
}
.platform-pill {
display: flex;
align-items: center;
gap: 10px;
background: rgba(255,255,255,0.05);
border: 1px solid rgba(255,255,255,0.1);
border-radius: 100px;
padding: 12px 28px;
font-size: 0.85rem;
letter-spacing: 0.1em;
text-transform: uppercase;
font-weight: 500;
transition: background 0.2s, border-color 0.2s;
}
.platform-pill:hover {
background: rgba(200,38,106,0.15);
border-color: var(–pink);
}
.platform-pill .dot {
width: 8px; height: 8px;
border-radius: 50%;
background: var(–pink);
flex-shrink: 0;
}
.platform-pill.tik .dot { background: #69C9D0; }
.platform-pill.fb .dot  { background: #1877F2; }

/* deliverables list */
.deliverables {
max-width: 760px;
margin: 0 auto;
padding: 0 24px 80px;
}
.deliverables h2 {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(2rem, 5vw, 3.2rem);
letter-spacing: 0.06em;
text-align: center;
margin-bottom: 40px;
}
.deliverables h2 span { color: var(–pink); }

.deliver-item {
display: flex;
align-items: flex-start;
gap: 20px;
padding: 20px 0;
border-bottom: 1px solid rgba(255,255,255,0.06);
}
.deliver-item:last-child { border-bottom: none; }
.deliver-num {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 1.6rem;
color: var(–yellow);
opacity: 0.4;
min-width: 36px;
line-height: 1;
padding-top: 2px;
}
.deliver-text strong {
display: block;
font-weight: 500;
font-size: 0.95rem;
margin-bottom: 4px;
color: var(–white);
}
.deliver-text p {
font-size: 0.82rem;
color: rgba(255,255,255,0.4);
line-height: 1.6;
}

/* CTA footer */
.cta {
text-align: center;
padding: 80px 24px 100px;
background: linear-gradient(180deg, #060E18 0%, #0B3D6B 100%);
position: relative;
overflow: hidden;
}
.cta::before {
content:’’;
position:absolute;
bottom:-100px; left:50%;
transform: translateX(-50%);
width: 600px; height: 400px;
border-radius: 50%;
background: radial-gradient(circle, rgba(200,38,106,0.15) 0%, transparent 70%);
}
.cta h2 {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(2.5rem, 8vw, 5.5rem);
letter-spacing: 0.05em;
line-height: 1;
position: relative; z-index:1;
}
.cta h2 span { color: var(–yellow); }
.cta p {
margin-top: 16px;
color: rgba(255,255,255,0.45);
font-size: 0.9rem;
position: relative; z-index:1;
}

/* mini dolphins in CTA */
.cta-dolphins {
display: flex;
justify-content: center;
gap: 24px;
margin: 40px 0 16px;
position: relative; z-index:1;
}
.cta-dolphins svg { opacity: 0.6; }
</style>

</head>
<body>

<!-- ═══════ HERO ═══════ -->

<section class="hero">

  <!-- Main logo (Sea Blaster script) -->

<img class="logo-img"
src="data:image/webp;base64,UklGRp6bAABXRUJQVlA4WAoAAAAQAAAAqgQA4wAAQUxQSEQmAAAB8Idt2zMn2fYdxzUlk0x6JYUooRgChC5KL3aldzsqcN9y0zvSLTQ7KljoVaQo3QaiCBJ6JwkdUkjvmXYexx8JyWSua2aujCzPExETAP/v///3//8dFKv6f0JBADBExjzes9f9n28dHRkVLFVAfHAIoia4Xsfha86mZZRTVUvT0zNu/7VwSNv4aH8J8N9CiO4dBrV+49u/MwVXrBJXJDbfOr/3oxdbRegAAP99g3ZDdMswsOfKU/k2wfYmZiJhzT65dU7vWP2/bRAknXdo2yfGfbn8vl99NLlfkxhfg16nlQDdLa+40YeyrMSOKMqyL22f1NRb++8Z1IbG93ln6+X8Mqq6NevmidWLZ43p07J+oBbQfTI0/eKOlZnYMYmZOWvX2OY6xH+/IIBfu1GrjuYQEXPVBDMTMYucCwe+HPNcIx83CRMmHbESsSMTM5UnTegSjP96Ad++35wvEMTMxHYkZmYishbdPLpsZFMDAKCb4zvoWCGxLIuvbHg54F8t6BX71i8FVnZIImtZ3k9jHg3zQjcGDW23FhDL1lZy+KUoHf5bRZM4KclKxA5LzCJn/8T2QW6LFD3lChHLl5jL/ni9nvbfKYGv/F3MTOzopRc/7WB0T7yf3FjC8s/bNTzqXyheT61PJ2I5UlnKt131bojfnKtWVkKR88ujGo89nZc9dSg/n867bUQsWyr+sVOIxr3QN9stWCGJCpc21nrOoaQxxjWvtNUTIybbcdLwp1o2b94i2ksClIlUb2qqYGI5052Vff3cCd+hR62kFMxsPtjHy4MN8T5+jzRJaNVn0szlvyVVevJafpk986+fSEo6sfuTaYNaPxJQAR1M6ra7kInlTWy7vSTObcDAubeIWFFvTK2D6hpWkLSVa6RKUAIJVSYJATR6Q0i9uNZvzf30t8vXrt7MLim1EFdKNrYrCWZmMpfk3E4+8NmrrUINWgR0GClo/DUbsQJS2Z+9jO6Bpv6GEmKFFUVrG6BqpvExBkQ+0iTx8VcnTZs5e+b0yWNffaxly2aN64eFRAX7SqoQVuYTGte8w/Al359PTzfxfYkdl7hi+cUNk7o3CtE7CDZeUU6skFS4tCG6AT59jgtixSU63NVL1UIARK86zVp3eHLY7Hc/33rk1IU7JRZbRYup9G5K8rnjB9au2PbtB692jtEBAqo3WAF1wc279Zuz6rdLd8tIEMuXmElYMg+vHN/WDwGwhlDb4WcTsXKKfd316OJh4KTrrMx0aaiXeoUAmtinJn7588lzl67llJbbqCJXkSoVRMKUlfz7x0NaeINaiwCgqdft9Q93nkpJKxVExEwsc2IiUXhu/dsNJahZ1PY8LlhRLWf66yXXLvrTXKFU1ov99OoUgtbv4UGrr+SXW4mZiWtYEFmK0/dNbBOmU10QNcaQxKFL9qYWlFiImVhZbSWpW//TNlRrPwwYnmpjZSVxY6geXThtwjYTsWLbLnRCNUoT1uLN706bmYnYYYmZ7u35T7tgtQQrSCENOr/+yc+3uCKxEhOTuLfrlcbe9qqzuIRYcSl7ZAS6bJi4j5Wc6I+6qpMU2vl/q0+WMDOxYxMzlV5Y+lQgAKDKgRWMjXqOWflbaokgVnIiZs7/Y2Ic2kPTYkUpKzBx7qcxrpq20y+kaMy8NFBd0reZtOdavpXla7q1uaMXqJsIAMa2b6w/c7fQRuwcKf/IU3bAVgfLWaELJxnQFUOvwaetrPCU8RKqRWiI7vTO4RJBTCxjIio5uqR/MKoWkjG241urLpTYiInYiRZ91zmoaqjvlCxIqTi3F7jg6D0qR7Dii3NdJdUHAUBf74npP6fZmImVsOTr5hpUHRAAvJsO+uC3NBszEztbur28uaYqvv3PEbFSEx+Lc73Q+408YidoXRWs8iCgFPzkwv2pJiZWzLJ9bSVUFRAADc2GfXI4y8rEzpnE4REh9wuakmojVnDLJ/4ul+/wm8TOkG60UndQF9Tt/YNp5YJYSclyprNWTUCtscOk75PzzcTOnHI3NNNUYlheSKzodP15dLFC38sQ7BzFe6jaIEo+HRefKmdmYsW9NzlKoxboIp6duaOAmYnY2V97IwwBIpcLYoW3bYp0qbDOVnaetxupNV4Nuwx7/wozEytywbqu6kDg0xPWpzEzETt/4rxlLTTRS4uJFf/uC5IrFbvM5jzI8rYqg2EvfHQ4OdfCCm69NFjr3iGAVG/khuslgl1HKjvy/McFxMpvW2ZwnbDOFyXsRMUab9VF8m028UShmQSxolPqc1p3TjKGP/HJxVIbu5iUW8ZO8XpDlwkjvjOxU73YFtUVbfgz39wW7AzFnnrumy7ihU+TiomJ3fWXEV0jjF3BTrZ8kS+qKFjnpXU3bMzkDCh7vMFdazZ+000mJnbfF0ngEmOLTeXOhnfHqii6QbszbcRO895LgO4WAhjazz1VKNjNP+jvEmHEShM5nUttQSXF4B6bTcRO9W5Hyc1Cr7Bnt+bb2P1PjnKF0Gd+OTvf9O7qCAY9uSKN2LmSbVd9twr1LSf8kM1MKkBGexcIjcOL2AknNVNBEAzdv0wR7HSp+P0AN0pqMPVYCbEqSIVvoMuDPsNvkzP6oQ6qHhpD05W3TIKdcWpXdJc0sZNOFBOxSlA0yuVBw7Bbgp2waaER1M56/9mbw0TslOnnUPfIL3HiVVYRXSA0jM4jdsZl87zVDARN3KBdpcTOu+wN9wfR5+n3z5hIVSgc4eKgz+tZxM6Yiqd7yQkR0b0B3cu/Zgp2ZnwiHt0dKW7e1XJWGbO6g0uLxpE3BDtlkTkU5QRuDhrbfFMgiJ17+UKjW4Oah6afL2fVMTXGpUHfsRmCnfTFNuDwCBqNPjAkNLROuyGvvDKgeUiQjxZRckMCn1iWTuz8T7ZCN0aq0+8Iq5EXwlwZ9B2TT+ykaVuggyH4xLV/adi0nUlJSefyiFlkJP360VtPN2sUrgVABHQTEHy7fnbDxq5gzls698Wv75p0UiX2GV0Z48hMYmdt+R86DgKgf+MB7+1LLjFZmYiIKyUSprRjB9dOHvlCw3CtuwDRn6WaiF1C24+Rbkv8d3ctrEYSz0N0XbRDrwt22tlNwIGlh97ceDajzEZsTyFsxfl3zvy6ZLDRHfB6ePglwS5jRle3BDVxM1NtrFJanndhsMM5wU6b1qGDoBScOHxrllUwE9tdCMFkMx0eFomuXvSYA2XsQtI8dwRDex6wsmp5MRxc16if2YlndgfHxJCnVyWbiIlrXjAXrm/m2vl021TIruWf3m4HSs2X3yJWLW2fGFwX/TwrOS/zN0GOoX161TUiJnZQEvuauHBY98MbVnYxixu5HdrnTpezekkXH0eXBZ++yc5bnHxc4wiaOtNvW9mxLavDNS4aBvS8xK4n9UN0K7SNFhQyqRil7/uBq6pJ+JOcF90dIoED1p94QbCjU8HsBjqXTBM3/y65HkRzwK3E538pZxWTxOFEcEURUWts9kkxO2si0wwj1DgaeuwtY3I45vw/3op0wXQ99xaxC0q0yK3wG3aVWNXMH6J1Slj1KmFl3vU7jv1i3bECdt6mtUEarCGEyBmXWZ7EOavj0cXSNV6eK9g1WeJGaFpsymd10zTTS3JGksHX16+ir6+vUY9V0BjrvvDegsELf76ZW2q1sfOm62Mf8jXqsWa8evxWRjJhZsuBpi4Vhg0/Z2PXlGi9l7uAmufOMakb1q3xUZGRkRGBWkBUPqyAXkEN2vee993qtes2bFy3ZtXKZWOf7tgwUIcAEDXk22QrsWBiJ287s2btymWTn+/Wpm6Qj4R2kR6efo/lTHQozoXCZl/nErkozH8/5Cag78CLxCqn6ejW7du2bd3yzfihg56s56cDVDaU/NoMnLXy92s5Vqpq+b1bB76d0DPSq/WGbGImYufHTERkzkq/sHPVglc6hUtYLW2XH4qZ5MRkXR7mMul6/G4mdl3PNXYPMHTuLWLVk7hSUXgv48bhH1dP6hIMAKhECCA1f+XT7RczSomJuSrMTCyKbv+++aSV2HUkYmYmZlNW6v4PhyTqAQDvp3vxvIVY5pTxmtY1kuoszBLsyiY3R3dAilleTqyekhBEJKylZ754oa6vhKgwqA9rM35fntlGJIjtKwQRsUtKgshmzj308cCEIC1W0CV8W0zEshdnHkNXyKv9dsGu7cUmCICunq7NFhuxOlv+56L+CX6oJBjQ5D9b0wQxsQtPLC59O6SBAUHz5B9WYiUUqwNdIP8Rx8zk4hyJdQM03Q9ZWLUlS+bhpX3roFKgb+flR/IEMbFLT8xkSz8wq4nfy+cFsTIWvQDo2qAUvTpXELu4pyeOGze6f4KfVqOREFBuEgKgpKmuhACICoZS5+NmUm+Yic2ZB0c10aHcECVtq4l7b1qI2D0kLjm9I41YMXfF+PvodBpJkhBQckGMLxwTxK4x5ZzbuvDdyQNaRHlLMtL6+ITFxXceMfvd6k4b1Do+LsTohYDKpOl0jVjtJabML9vrEOWEAY3/sz+fVUzbrUvnTh36csrYkS+2qR/jLwG6Fr4TrhOxC0wVmYmZSy5sn/1qx0gJANCBEABBF9jo2VHz3l1z6NRt4uqXXjl5aMV7017qmBitRwBUmnZHhfrDTExXRjxi1Gg0Wq1GIwEAIgCg5BgIWHfwx/8UE5OKwcxExMxsuvLX7o9H9mwaIiEAugg+U7OIXW6i8pxLuyc/V1cCR9JEdh+1aO3fN4pNZkHEdiUiMpVlXzqxf8GLTb0VButushCrxLmHv5w7f/78+XPnzpkxZdyop+LCdICOAVKXzZkWYtXzPsxElqLbSVsm93xY5xpICasLiV10UZp3/f0WgRpHQNQFJAz47HJuicnKjkmmwrQ9IxL8dYhKgRGfl7F6TJby+5aVlZbk3k7e+s7wbuEBBg1ijaBP848zrazC2krzb2wa2TJIJ6GT07Q/JNh1J2KRs3foI8YaQvCJf3bSnkwbMxM7LBGzLX3n+JYhkkKELLOwmkxVZ2YmLk35fcmwdvX9EdBeuvZf3BWszhIxi+wD4zvHatGZYZvDgly4yvMOTW8k2Q0BMLL7/MNpNmYmdnRitpz6pl+gIvjOLmd1m5iJuPTSL0vfbB0m2UXz0KgLgkmlqUjE1tSdYxKMAOic0DD0OLEbKAqOvaizF0jNRu27VkosX7Le3dxNXw1EGWDfmzaVi5mJmYmsOZd2z2qsq572+Z9zWf0lUXByxQAfQGeEgVPvCXYTS37q4oN20NZ5dmOBmVjuIu+HIU89/dRTTz75ROu64WGhfjoJ0cGw6QFiFZ0sOXteqe+DVTG0+aaAWCW2mf58ra4enQ76vpMr2F0kujojqjro1eTVXXnEyliaV1BQkJ+fl3Fi544fPnt7QOf4CA2gA4V+Z2FVjZhLzs1tb7wPNh5/UbBqTMxlB0bVQyeD/hNyid3Jko2Pa7Equg7TDuUyK0UViZmpODP5j81zhz5WV1cBHeF/JaSqVUrms4taSQgAwcP+KGRSjyot2vNSoHMJnJoh2L20nn3VG++ja/jerSLByi1IlGXfOLJiXMc6GgSssUeusipP5ZdH+KOm5ZosIladRcbXDdCJJPxoZreTzB8FIQCiV9MPspiJFZ6ImUX69uGJEboaMnxkJlWOicy7u42/y8Tq9PWhQegsmvzMbqnpgwgJjO0nJpnZSRIzlV7ePKy+HmsAW5wkVu3FzUJWrSnrwzgJnUKznRb3hAsWhUXPPV/MzpXo3h+Lm0n20w7LVvGYWMWiom3NEJUPE3+xsrtatPb3MmLnS6brcx7W2ivmR8Ge6taLA/SKh02PsAptPjryYa1dsFs6eawx33nVoHDY9hciN4acFlHxT/187aH91Moe7HS6vaRo2PpXM6vU1pvvBgBWK/IWe7RbNuoVrcVhG6vXlt1N9NV6xubZxrZhEipXk8PEKjbZkoYYqzObyLOND8WAYjffTaxu043RUtX0a9jTPX84KhTW32FmtZtyX8cqRSd5vIl9cahIGPyljVXwnDcNeD987I7HGxeM1CkSjChgVfz8Uzq8DzyZ7vnGK4IUqeUVVsdtf7WrwhMecHQkVokiv7epZGQ9FI5YWQ8POL7XVYF8phawWi6sX8YZED3m+D1EpcFOl1hFL/x51tPBAICecfu9FUf/tU1NYyq9tmVsU/SQK3y3iUZZ8LkyVtuF+dbU2Kc84thy7ePmXkoS+Qer78SWn2ekecQx88W3YyTFkN7IV+GYyZZd5inHeRs7SKgMGLtLqHKe9eYr/RRC+0Y+PwAzb5RRCTDoG9uDMPjOKKMSPHqVH4yZ9qb8EEaLB2Rwdm9JboDb+EGZdLYdyi3k+oMzTEuDUF7YufyBGczXntPIC/5jowdniEOx8sLZ4gEaLBbqZWXcQvwgzTttZRX1Dz9Q0/KZUU7x5x6sIS60Q/ngs7fpgRqUNkiSD7yaLR6oweWzDTJ6LecBG+Ijo4z6Z9CDNXh9mCQbbH2FH6xJe2I1soGGZx+wwTuiZRT+Ry2BEB5za0JRPvovqHYg62CRh5z43A/ki6NsVCuQ2XlBlofcR0b5ID5l41rBe3GBL6V5xNkW+cgHIPR67cC1SElaQuQBd+81jZxgb+3AXo2Eg8s94OhyB5QRwtzagcWAELWTyfPt91g5ATxxrzagvC8AYJtfyokEC5PVc836lQ7kLEX/SrUAlxOgYp3Je85dO/vDxizPtaJeIGdtvbHJrP5bvguuBKTg1t2bx22xeK5djEAZhf73QD6pf3Sjp1QZAGo0U4vIc22+BHJF3wHHS4lrAS3fhUIV8fEs9lzPbA4yRW2TD/O4dvBWD6hq9F4mjzWxMUAums77yriWcLWxKl6TCtljnXKHamSCz5yxUC1BfkeoavOjwnONkxJBnkHvFHBtYdl0LVYhZIVgz/WiKXp5BM3KptoC6466UNVnctmDPakJyFI7O4trDa+9oK2KbhN7sItpOlkYxhVSbQEVjveCqvYo9GS7/hDIMXhmPtcWUtlchKoGbRHksUYlEwFl4DPjHtUa2HZEVUnqc4c9120/1QXHR+ydxbWHRx+ToKrRm60ebCnP62SgiTvFtYYi5RktVFX3v2L2XC96xxscH1vvsdUakGmSFqoqxZ0lD7Yfw1AGUWvLufZwVxhU0afR0wus7LFOdzqADHVTC6nWgA41h/sidNx66lYBe65b5uscD3WjBNcaWnc1hvtqYybfIyb2XLesi0LHg44pVHuwIxEql6Jf31XAxB7str/agAyjNlhqC4guNILKvZ7Zmkvs2Z41UCcDr//mcG2huD0AK0HjuJs29nAvH2dAGbRNodoCW/IQPVSUYj40E3u458/2Bjl+Lri2MP1lb6goNd9oYk/3ggVhIEOsn8W1hvO8pUpit5SSp5t4PwzkKC2k2gLz+hCoiL6fWdjDncxrvEGWDx3j2kEybY6Fihgyw8ye7uXb6oMssVca1Q6Ik49jBQydncee7padiZI8jAvLuXawcKAOKvrOyGaP99QOGpBnvf1cO5j1ioQAoIv5xMQe73n9JJRJ+ytUG0DF830lAPAffNDKHu9p4zQg16czRC0AWffHIwB4T71lY4/3jLF+IJ/MWgASR1ppAEAzoZA93kXpHCPIt9NVUv2obFd9AAC/MSXs8U7WH4wg4wa/s9pPJZsaIgJ4vXSHPd7Jsr85yin8B7WPLFviNQiALf+2ebyR9ee2EtTq/BQlIQAE7rGSx5ttX1MNyLrhAbXvZltEANC+wx7vZPk1DkHeXa6TundvjB4BABPOkcebZX9rBHlrhxWyik+U8lYgVPpqnqcb2X5rqwV5S75LScUj69FmElQaslGwh7ttTyMJZK4JWK3mWf98DLGyJkfYw9366yMIcpcC16p3ZPurqw6h8qdukkcbWfe3lUD2GLRJxTveUYdQudeYIvZkF9ZfW2lBAescUu1sJ+MRoXIpeBV7slPJzjgEJWx2l9V5Yfmzi4Rwv7DN5MmWsaQeKONjJeoc2Y501SNUIXSDJ1vWxCBQyA7lqhyV70jUQJUjd3uuUcF/DaCU7UtVuZwFAVDNZtfYYz1jNChn42tqXN78EKjuU8Uea2njjMqBoTtJfbPMC4ZqTxWeacSXh/qBgvgssKltImumFqq/lcgTjUyHGkigpJrul9Q1sh4ZbAA77vJMK9yUiKgoGLLGpqYRHe6sB3vu9EAjzpsdKyEoq/RWLqlo4lIbLdpllweaKBnvh6C0mHiRVXORv+4RsPO3nmemI721CMrrtU41oxtTI8Deb1rYw9y6vY0GlBiHEqlixEd7+oLdexR7llHxV/URlDnqBqvhIv+7eA3ar026Z4xNOAnb7bHBCEo90+ysiMh9EndH+yPUYPTv5AFDmZvOOAdx6Fk9gmInnCRnRMz5Ow6a3SQSZ17XQU1KIWs9YMp+ey309XRSPirc1AyU3DinzBlx2f5XYpotLya3yLy3ix5q1mdWuYcL8fVZCVoMWlxKipc9JwYVDRL/JqdjzdnzvJ8Eks+EAnJ7yJY1K1yCmn7+LnmykC17U0MtAEDIZoWjsqPP6EHhvcYXORcSd7YMDYZKNROu2MjNKf69P0LNx//Fnqz3vu8XAFgBEs4rmrj98UOg/OGbmZwFMRUe/7RvtAT3NTx3yCrcGKJ77zTWOoLxM7OHCjEX/PhSFNxf6nuVlEscHBIEzrDheWdBtsI9/eP8JaiqrvVf7oxIe9UHHFIanE0uCKXcJLVLlFuUTph39Y3UYBXAZ0IOKRSVfvWQHpyi9MI1cgJkSt/+dmMtVD/kk7tWN4Vy1zVDcNDIJHY5SaS173bUQuoDUUFqWrkikMj88tERl62kYLYLnz2jgeoap+WRElHZH329wEmiz9uZpHBE6b9/ODAYALB64Dtgr9ktoZvjI8BhpY9cDCK2nBgGmkc3FZMLQFYmIptwEajgl9Htes+/TPKjgn2veIOm29YCxaLsTZ0MAFgdCPiwTChQ5uJGEjoLgKAvzUKhiJjZduevj3s2NCLYW9vgw2w3hJL6eoMDt0h3FYhFzoqlf53aOOlRHQDETLosnJ55/9hvD5/Y8s7SAiYXwPbPqIYaQK8eP5Uxyez86PoaAMCHplwnUqTi3S9HgX2jlpWQ0pT+9oo/ONXI1aWkSGQpzUvZ81ZiqFFCBPujX8/9BUxKYb2z+aSFZGXLXbPgtlVuZP21jQYcWTfD7BKQKE//sn2AMTQiQI8AAJJX4seZVpKVyPvlVBmRfCzJE6N0fmHhgV6+A06ahExIMYQp9Z1YPVTURI6/bib5kO3et430ULmh3W/lQmnIVvBb7zAt2kmKmJsuSEksN0dHa8HJeo9OtZLSEOWdX/5m9wgtggP6v3quhJSArHfWJkLDZfdIPlT6Wx8vfZdthbIiW+53DcHBY3fbnB+JgiPvtPSGarf77rqFZEOFp0b4hU+6bJaL5cbnCQj3xbqzL1hIDrZim0KYz7zbQIIqxi86VUxyyd7STQ9VDZl2xkRKQuL29719oCZ1zx0rI8UQd5Y2ASfsO+hvRSFicf37kY/5IwI4BGC7ucdLmElOxGQ5v2xgBAKEvHXcJAsiptuLEjSAEDsj2cokD2LK3PbfUHB0/X9zhVMjZtvNHeMStQjVRYCgZ5alM5MsypKmtdIC6Ht8fYuZHIyIRPJXz/tClb07fXNbEJMjEXPh9kkbCpiJZHfni8e8oeqG1tOPmYjJ0YjNR0dEIlTd8NiSixZmUgJiFjc39wqXAGsCsOXn6aQIxHlbBwWCU9Y32SWYFIKIKXt5t0gtODL6Nn15bwkzCZkQc+mh2W2DNVBR3+KdS8zkaMQiY+VTgVCpseNHt2Uibi3vE6MDx4/dYXVixGw780HXGC+wL2LIs+vzicmxiNl6a2ITHwQAkEK7bsgSTMJhiJjKz733WIgE1Q196usLZcTkIERMdze/XFdfZ8juAmIiGRGbfno+GKrv3XTCX+XMwpGI6fb8RB1Ctf3bzkiyMsmOmPn2su51EKGmpZBBSUyyIxbHX47RgrMOnZ5crhDlmUcWt9EjgqNLAe2nH8gotDDJgEpT1vf01yFC5aitO+t0rs2RiC13d41q7INwX9QnfHrT5mDE1uyfJzXykkCO2P62syKiwovf9QnXIYL90fvx7+6aHas87achD2nh/uiTMOZIjonIEYhFSdbpj54J1yHYEfWhT3xyvojIEags89A7zbwlAJQCWr64726BRS4kCv8Z5CeBXbVBXT86kWV2HFth6neNdWBPBG1Y/52ZVrmZbm9+pYEeERwQNRGf3LSQvKj8r+lxEjhxr0cXXzTJipiJzHf+XPR8hARyDerx9tcn08uIicmBxL1fZrfWI1RT2/DFTWk2ZqaaI2ZRcvnbZ/yguvpnt2cSMTkEMZMpLWnl0ACQ79gickpUfnXXqHgtQo3renx+ppSYHENkH1vcLQCqHTnwowNpVmJmsgtVQqLobtKWGX1ioAZR88iEncnFRMxkJ2JmKr+5d96zoVBFDOr01jfH08qYHIuYyZaxZ2wsgt1Rqjvwk78zLMTMZD9iZrLePbLmf4k6sD/6916VUmQjZiZyOGKypf+5uLMPguN6dVt5SxCRXKjkxMIYcPY+XRZfEHKikis/vtunkQFkLfm16jt9+fdnS4kcg6jk7IrX4vQA1QKEiIGfH8kXjiCubZnUJRjsqIl9eWWKzUFExv75vVoEIMg4dIXFGZX+NvOJKAmg5hDQ99FpfxQ4ApXf+OnlRB8EO6J3g34Ld1wpIzsRmbNO7/5idM/mwVqEGgHURHUZu+1cEdmNis9smv18XR1CFREB0b957+kbj2WaHas46asBsVqoQQQA78YDF+2/ZaKaoNLUHxf1TwjQQE0iQFC3t5f/nmkhOZgvftK/oQHAkQCCe6+7I+RScnxWW29w/ujf4tNMYnIoIiYiYSq4+NN7PRPqGCWQP3oHhse/vOp0sSBiZrILMTMRifT9H7zQKFgH9tYE1Os6fftlsyBiEvYgZrJc/XFG83ADgn21we1mHiklZrIbETNZ03+f3yXaCDKXWh91MkTWG6v61vVGcFzvh3uuzBfMZA9BFUhY01YObBGpAbtLvnUa913w05XCfLMQgqgCkRDWtMOrpw95vGFkgB7BMfUR8c+//2tKtllQFYjIVlZ6e9+Cno3CfBDsit5hcY++9MUPp4sEEVEVBNlBEFPR8c9faBAogQNKftGthn588GJmuRBUJSIS1tLMQx/3b1rHVwOOqAuq+/gbn/9+KddKxCSo5gQxkbjy/ZtN/CVwfCm044e3BJPDUcmeofWNCK6hFP/BqWyLoxCTKfvGma0fzumTUN8PAABBGREBwCe+/6JvDybfzCkrt1XDXF6SfjXl8Iolk7pGSgCAaLfKA5r0mrf+xPV7ZeXl5Sbb/YhF2b2UXRPaBiPUJAJ4tZq073qOhalaxEzm3Bvnds7tGqUBQJB/60PkPIiKr+0YGA4ACA7ecPSuq7kWJiJLWXkVSzKvpaSe2b7kf+0joIYRAQAC6j/c6rkXR89cun3Pnu1fzRzVp02EBBURwWERAKTA2KZDl/6akpqSkpKSmrR28TtdH2kYAQAgIdgboaKx4VNTFi74bP+llJSUlORzyWnZBUUmqgpZ8tPO75nQ3BscFgEA0C+6ac9RK46mplSeemL9woUjWzSK1gAAIjgmAgCg78NdZm47cTMjO6+wTDAzCaoWCWYy56RdO7pxcpdAAECQIwJEvf3rrTImxyEqOre0uwFcSUP868v/ySGqhMgOdB8quf7P5sWvd433BkBQaE2dtt3fePeDZb+cPnP2vknblnwwo3/7NtEaAAQHRdA37Dx0/gfvv79g+c+nz5yteO7QqvlD24UggiOGdX7j63/STVQFImHOvHRs85IR3Zr4IShmm5NOw5q2b1qXAJAnBnR667OdF89u/+Td96o4c1D7tm3jjQAIDosAAGjw9zdIAIAgWwQprG2lj8bpARDBUREAMDixTevWbVo1bt3r1dGTF6/Z8tOevTu3b9u644f1n4/q1TwAERwfEbQPPdq28kcb6AAAQZ6IPg16DHxl+Pi5327//eilu/fyS8w2q6nMJIhIlBbcu3Xmjy1LhvVuH6sHBFlj5DPv7UouJWaiGiJmKrtzcFYLLbiYiEHNhi7Ze9dage0k8lIPfDaya7NwbwkRFB1RMhj84lq3uX9iHR+DHhEBHKgiopfBYDD412vVpvJHgrwQARwDUApq9tzEb5OSr1R67vsFcyb3fiwx3EdCBCXtdtw5iDMf9npYjyBblHxj2rWJMhqqqseK4FDVlRUAVg4AgODgWEWNzjswPDr2oZjIOhGR4cG+GkCQJSIA4P2homwAAAFQ4xUQ2aDpYz16vfzfKTOnTxw9Yd6ydasWjX6tV7fWj4T7IIICIhpi2o/ddstKXINUyZ2t456M9wGXVOMTGj9g5sx3lh5ITr2aVWqqtDjzSkrqsa/nvDNzWOu4CF8duNXo5R8dV6/S2EAfg5cECqzpckyQspEwpW9/OdYoQW0ranReBi8vvd7bL8DfR69FUFh9cPyAzw5mlFgEEZMQgqpAxMJSln961djEID2Cq4oAgIhojIqJSXxpyuTJk6dM6hsfHRMTBIgIAIDgZiNUERERlLnNj6WkXETWW/umJnpDbS0iAGBFUGAEQN+EQR9t2v/nP2cvJV+/m5mZmZmRkZmVfe/K8R8WjGgXKiEAgktbAeyJiAhqdcxnWUxKRMycf3RJnyhE8FREQJD8oh5u2LJ956f6DH3ppReHDB762usvdYwPQkAABA/E0OFXBJPiEFPG5pcSfDXgAYmShAAoSRIiShoJETwYtQ3X5FiVhYQlY++4GG8NPIjSf8D3WaQAxPfOmolIFJxf+VQAAsKDKaWot06XMBPJRxCzSBndbsqKvw9+Prx9MCDCgyv18S/vLiCWI1EFsuUd/aCTD+iDH4711yI88FKXMG17spnJoYitprw7Z35c88Hghjp4sCYaH196IKWwqKi4uLi4qKi4YlFxUXFRUXFRcXFxUfH9S0pLKuYm/7Zi8chn6vkaEAHwwRoAENCw04BBDjhkyOCKfTo2CPFBqIjwIE4EdGRA+H///7////ULVlA4IDR1AABwqgGdASqrBOQAPm0ylkYkIyIhKnUq2IANiWZu/Fpv6ZZecMqYslwg/qf7h+6XdPan8D/iv2h/uf7ofLlw/01+EPuv+P/uv9q/az5Wf9j+vd6fWP/W/vPqQ+cftP/L/vH+i/cz5k/7r/kfsB8Fv5B/nv+J/mv7////oC/hH8X/0P9U/yf7QfPn/rftB74v7r/4Pyk+BH9O/1X7gf8/4u/+Z62v9H6kv9Y/8v//9v31Zf/j6l3m5f+T95//t8uv8y/0v7o//D4Qf7j//f3Z7v/gff8R/ivWZ4V/jf7r+P/by+4vpj/rf4T5x8GdqX8x/D/9L/E+1X+5/8X+i8ZfzD+d/Zv2BfxD+T/47+8fkPxvvC+YX7kfc/2E9rCfT9v6gn+B/3Hrj34f871AvJ1/2fKX9hewb/RP7x/4/8N+fPhGYsI7xnTk+Qlc9WfISuerPkJXPVnyErnqz5CVz1Z8hK56s+Qlc9WfISuerPkJXPVnyErnqz5CVz1Z8hK56s+ONzftRdo/8wvc45CR7y9Npna0Sk1hewDKZk+duXiJ1h+XNf+X1vxs4cSzb1H5freaQlc9WfISuerPkJOdXmnCLCcnydFX3IwW4SeJDW8ZQRADRPnbl8hK56ifN3RdkUyXCL96r7vrreoshhJW/WWSXT3HCaqBqiouT6ujoFp6n9OLNvn1muRXTR366AY5UOYHtPm1ce33MagyfveGWi92ZmaJ87cvSI2EBika/9qYSiX/eetG26QE4A/vknVsJbY4E2+vGtn4Y6geEd4zpyfISuFX/EeWR8e87D+gq/f7vX3hT69HCuMVpy8eJw7pJfD9cuLfsWlrnqz5CVz1E+b4cwq4TwSand0vPORW5f/N+4OpSoYOEtP3+lHLkXPZXykAzcCXfEkXRUKba82qj5fFk2KNLZKb3qJorTLwN6YOdiOsqw+HgH3Qlc9Nw18iessfN+HUhaY1IbKpx+DRr/9gkNfyNJ5/r+3yNRjftAHNrZl4WdrPVnyErnNXGJXScz8x/H//mfc5JxX5YZeD/99U/y8+cUFJyqWEp6dD9L/U9s232sdpETnbl8hK3JdW8DDR1wGTMZzRxP+S673gyO1Tpfvcs/1PLeYlKbqiKv7tx/i5mX4EbyJBoy6XLUMJNyWkmbkHMwLRy0bauaTinBrDP6+CLER7ypv2lsv/1NsGdzIisS5gBfZ2ypXwR9OiW3/vM4DU8qnOY+foz5wj/JqNpsYGswA0VE/0siCI/qp253Fa2SiLS8S6avr+6/+GxQaOYvdX6Mdz6A92l6AiBMEKvhHeMuLddqo2/yvgKD4GeP/+La4DgX+ljM//0uNlej3gaRR72gcSoq/iGtjNqPaiT56NluiVX0rvCu70l2rLqV3pKDGJOb40Q766YSn17XIrE8qnHn429l1ZpiZ4ewlIS9zRwG502e/2zGDAybDFF+9ArJstxj+TdLH/7/7hIsJk0Mhzouu2kTurOrDbagtTEV2znN/mGCODlXqvGjlECFizXNWY1+O2vG5vIZ4qGtMaP/9QW/DIwa3eBlr+LBhOizZjf73yT5csGfzf6hlj4Uy34Rj50+y/09XH0KOS3yplq8OB8f4+BG1j8JoLGpviXzkkg1hNFDy45voOpbAfSZZNy/+7B2aEJ9taLJIp95zw3hqQQF4Gh+NWJrlDjZDXReLcRQT6jEXWlvQpNOUjbdMOxV3HvyFvVnj/SRBw0GMqLHZNxQmcKO8H00C9qrfLBCCFf/7/k/ZCzg/0vCK788SGF8mXLf/WsvKhItl8oeGgldy94SxbKJO//DMPEv+Zp6EunNFUSdCG4+B9PI6f0wJ7Wowfij16Ix615U10nPttU0e0ETeDWalZR0Q6dRC7BMjGZDVSIKYSHHe2jC+gabeMDVipVBb/9G43/OfZ5cJTQgnO4k6+hMy0USKFRQXMRf6cHE7tkaUnFy3uuYDzsP9/eeh0D/ojsdD0xAPnzIwZglpljDlWcmCbaaZti4djvV5sQ7sZ2hGPfwxNESBlDgvC/gjImdpWLY0iubOqDrDrLpg3pL2c5mvfqW8e4Hhga14jEl5S1sfhJwGJVrun1+oroP9VijS3BMR2nN3Qavkyl/lZa3NQvKF90Q4Lv5Da1CIfBw7RkBD7ui+dwUR++RsIMnWpmbZZ2rD8pWxvWBCWqRF/z7NYwylb4OpYB5ZtFsk0Np3HP124s/GYLY6ihdVH89/B+7X2+QYtkx+zFLh2hJpYRZvJKrL90EP3KlPMX+8vz33tqRqN/Djl1V/Oz+w+52XaIKFx9eQY0/iVOkzscHuS5pB/2q56hstRvu3s8LjblKrpX5k/wJ4UNvs84owGFUlTV6q09VF9HqEU3yfAUR/M65cSEwDcdF3mkh9YCYWqERb2x8KQn7yIfvmbrQWyPxweIDqa+yMawIJIMN0DfH6skfxlHwmH5tZmSdBJwQ52e23S1WChTalOr52C3lMGRoqRwhpeX/6g5YXUGX6bD7rvdlBwrxVWCI/90f5Huhy7zWB3T8sE3AMLqOY86v+y+2uFg18iCFfRoxyjeiU0tGEi7M+HkbAiEXVDoB0J5CdXxjshtZcn4s5dlFJ//09KmFiSIbzdy6jAXKF0SWk87/o1qiHAHRk95g2e260FUDeEAlH/VadZHqgJlMjAamLB9sfuG6FHEgzrNJxt2u7a8BLH/xz/Qn7+/fpQpN+1RFRdnG/VT01uUNvSDZpkYuMyd7WdWC70YHClKXRu0hNIcG8N0mkt5i7b6J2LQO+warn4xH0yQSiuxptAd6IyWIa6SesJX2JwOO2UnBgF/RUTOtXJa93OHxuNsGvMGiqIk0MIWvsnx2+L0kWsjD18rIWLJLwtUVV3kxsg6xbIh2yVkCEVK36hONnIPXa4xtMmIzUXw/TUESjr60kUgw8QvzAUHXlj6oLo5y8cVWtWlbmhEDYekq/THh70tC8QKSi3F0hD3S3OJp3WY43v4mcG6PknRJilWGfm3jcSES/Ueiw04KjyLCmpU1tzLXOLkMhgk87mqHHKMAOl7tqTMqgDlPGR5CssFFXkXyv4TQlEWD6bfQ7FDYXEbGUFAEl0i+MGyG/72tIlTKEhc5qcDfe71JdV5YBbKeVEb+cvKZxwNQSz9VAm1Tc6yZGezYpFLG8EdlejKdJmsNa9sMVQI4zJRJvFIXVgoe3fh6lIgxKgjlwMJCKyupTW6DrWXWQQzSEi8u5DvLIcJCH2Z/nZrGTdXyvAtLV/y6bedTcffKo6hDnw4y/7pSR0fpkESJAq33HMhQZpYcAThFqa/k8iEqXgYcCdg6U+cgEkLnlU23RfI4JiD/w4alMXqX4ln46Q/t//U7l9eoIcX72Qgq0IK9QogGsTXI9mfgcN1BcSHvmcXiaSOdhIg3+P1uugHVC79rfMwz0Odg+EVILhNctfsbhMiFWgfhsaHJdWQ9pt1Hny/MUH4tw3y226b4UUVSpYSYjdU5CIdg5c2yubaV5NwH9Breez+fseI+HVsOnY9Q19lr7oeSwVB2ZuIACMoQMR7nxP4L2DKzraZ7OalzPldFT/a14qw6EFYtPtmeMK4m8trPLp4IjhmXGaj8z71/hXLcHu+NH4uvDXj2Pr/rka4abSLZmeS9+1SAHiJ2JzPLEt7NpiHvSwxM/1/5Vztl82ecmC2OmxP3pHlKpu7Fn4nvL5gXTYMdqoqGOW8BCL09rUr2d7ZBlxUB6Bq56Tl26AM0Uze3W1nf3nS1z8Y5o5mCo233Da79lYZCqn/EfPKYas+2fhXjlz4Al+UzaPT3Px5Qp56YGdrdJ7o8odX2RXyoAGXSJZsf/t2ccD5RrNHOh/97woIdNwdTcSUIP4gQLDO70g/B3Y3QaRd+wUfiwDcfDtfzIFj574w+G8HTeRnEj39wEXzWlOnEtj//PPMqzD6TlfXga4/x9wCAii5O4Ve1X/W9Uf/wn8LWT6b1X6O4nydNq+Mwn/uw1v2lV5jGe6//5HkvOr5dThBIyS9qz9xIYMeuGnIkqnt4eMbf0dT7N/3owO1UP0zhoR6ihR8Ny1mc42Sa+2GgJR/f62Vl7fsPhQ+Pf/nxUR+esP7VmNDHY8DYOrUgWLjoQ96zD2gnIUvP/J2u3VcNT+u3f/3bTguJfOpIif/7vrtVWOcbh6gQZn23rpC6EngNkxjISS1qjmK4daBvSHunMOJiS00Asf3CKKqU7htDfbX77QCR3M+f/iifnYr3QLzYpqMw/f5y3U0cFaLYPDB1pNl+V3ZsVNassFSfsnXXQApNC1ynOIHQGdMqlSI1OpQE3/JEiTMMy3Cj3ogmMZCx4k3idTlQZwPUzca+XlZr6RS6u1F/CdklFFVGt9/j/BPuHMCtaGYRgLTm3ZVghk+Fti1zToCZiuiVuMi3g1IVQ0n45iqy/NMlZ5YMniqD314bgoOXyErnq0wBK56tBhBaOdy+QlbkEhyUM8HAiR9YplyNIc9WfMiQGXWpn9BDp3Puj8pCDsVUb9nAnO3L5CVz1Z8hK56s+Qlc9WfISueyxqUzJ87cvkJXPVnyErnqz5CVz1Z8hK56s+HgAA/v1xwAAAAAAAAAAAAAAAmOvw3LhD4h1on4SxgMD/lawbZmfcOtk230MMTiIhT3rJYaybESJTFc28ik4Yct1hbpCBIXjTFc0gTcwf4o0AY/cyoQFrdmriys10PzTDaTQ6NTw1lT4tXLt+TMoX20Y7BVVp65i+CGlHWMBp/PxT2Ui9Dh8MuMlAlOmWU5kD2i6EwsGQGO2/xjLJe08NiYIvxpk8atMbwMbxDUNZ9Lm/bVETo8Oh0MgBz2b7+WxfgXdKyLoZyF0egOSlDn9xPqrM5sL3D3DESDbRrGaD/qwKbN1COEoS5953b/dakr4GiA796Xdnx/gOdfSrLl8Nm4tjEef68I2IY3uCY+q432P2LAwtsukQqUcCkBtvLHhCrhpm/PNRH30PKUXMFubI4eYynPZ1zt/PFxoC19HztY5HHsBom2Z3bmJhUu9opn0pfUVPMcd6kjM+7sg42xupsmevQAAJ+/7mE/HVuDFQ3QQtKfTkhe7vtSKZyWdEiJ3sDLRqvIUK3TlOAq9x752cgvewLMS1bMkOrzKi286Wn+0uIfsYem/6pew6P9O8ndJ8x4qhWB4mtdd782AhS9IsDVqfEuMjEj8EwOuzdFz8cPoo1WZHIpmHWayUytMzicuckxh+EAMg7ALi6f7kpnyBJgkT9MTNwXVcyAjocVueMBQAbI+pjYoF1kKoe30VXzurG0kIRWXNuEbUoWghKzgVlJnB2diNbP98IUS+otqiBYt9MWnX0AAC46KOIX4U6MeHp+OOtT4hv9RIxev1eWGd58UdJlalMgHiAP6hsBITnQsuN6l2Md2kedZ8ympxbsIck1Y/Y4ApEoe3fJ2jy1zPDoss83CiB+yCSXKFQBC1DFdRw/SLzsl2UZHUQjkMavS2hGVk6bXUXdsXlvLYHWoJFeTjn8IEIi6+2kwKL7rh2G8qanLqRBn90HfteEl6KAIvhs30lLv/Z8IyTSLaEJXsGb5SKe/WPRjduPSkKHgSVpgu/Y0rnewFISOokzIMdcQ2RxswDulEHLvIU5vDfcnCCHxlJpFmP9vGDi8PkRGoFECvvp7NcRgVjRZXY3oBdl1t4JFUtmc0wDKqp5X/jpmXS/Rig32qE5VN5Ar1mOXsaKsoXZYdKT7gejyuAI/jCJ6cswnF/v+ATYGRju0LN+TGqoa2foi7U4H9B5zxO3lgTfUEpz+5JdCdbKygw3e6xQMC84xCAXiBMYgWW2ElI3jrT2xGbNCyd0qws8ZFaUS3q0j3e5b4MXPd9c9UciOoBkAoh79oUnyh3XInC1nHsNXA6ESimsmtrnfe0+W3iRZs4yYdZy1mD8WzX2QHqxiSSsQWuA00HVG4lWFViY8W0b2FY60K5ZNSLDxPDdEElYec43h/rGibrJKH0PzPHis/Cm4QY6MIpwLwoD+lV5CFUbD7Y3qEKJYs4huQoH0lGBsXjz8USCDORetkxOc2V8NcyLRnPQQY2FMHcRBLTHlNFxtJSZ8DMzydCZ3IJVktP8qlFD3JuL0HrIfv9h+Zr1xsA8gAqY7FzxyRvC0g9uvqiz2sTnAVQtJbtk9ZGZvkho+ZvqxHAABXqKNGN6WNoalh/VvU1QToGSe7YB/aat8D5QsOSLxe7n3B8rEdXp5WdkU5eSr0wbPkYFJ2lcAHyFvnkaOx2pVLloFKPTPfFyh3+l81uc8V/GANWw1xfhVXW0WRMd/Zz+TLxoVW7xTvRLR9RE6K3PoONzWA308du2lCkMf0DRxfCSU8Kjksxhcf8+am+rlciZlmp1tQLBDL6QrivzFH8+amkhjuBWWiKEurcWEwM4PuqosCiZ9/uqiYMP8IsYi6MZMw6F1pbCxTbF2Ox9Ihw4zQg50RSbLMTHs1PkSDP1W/2Vf/nM7Zo8FzO9ktazKfGy/ba/FQdtMlBeAE+WA9C/eRiJ7GRLGk0Wg7GX54wZ8O8qVtRmTOhfgVC7TCsq6O4HQ7zxfJ/zlbitCPrRuvlns2TwCF960hhzbYfhZZrLJIAALkU322Dzz/ov2msRuq7uqRmJ888GnuS9+LpqmtdzvVrIR+KtBQiaE+qVjqVCvddhr1QSXVHkq0Jwt67SpJ1K9j9WGszzFgpfe/GGcfIZF3q0zbbHh4199XM1WSkjvy8WsnL680xch1v6jmAR00Z+jHiU+hztBXNTbHgulaP7nUiy2h9NIkaELln8EXFbgtaonsgYAK1E8a/EdNUG2VIObAVwjg6s4/guSPK/FOsw/Bq9unuleBVip6bmS6ioEn+RaTW2yMR1//GFKbqmLAzVfmfXf5jx/8UHRuwWy1dqGsLig+AwCt3KezNCEdnHM4u0NUBtMNatHPaQzDHTjbJJs4y5yDPtTtcn1Jgqusr2icpKXoaEGI5BH/frDeYl7+8SeKeGUYqyaJcAj0JkYZ+5BePBG9m5urvwdcXhKRzr3eiI9xf77V5KuM57sCHrCmvT8w1tJDtyGbrkWmCYQipXJr7i2nBbQAH7PnozAP8qWPSWXeBtBP1YWFFHGDx58nltP0aZJR3soDe+IF5Vl1YkrVKDM4yB1XSlXYDA0penjz1LT3mpW5LIi+qdliPJpm3i3A9MW+u5F/a5NWJt7QJIzhh/HfVWm0pjg3SG2kLh/wJezyPO3rX8uhkHPcg0RwgqqEMkqHh1wcDtjOpl4RcsrHM2z+JIkzoBJnqrviHy4kyR0bVDeG72KyaOFDAiTEVLUPAmPfyflZyTHFGKk+v0W/ITsBEJWB/hF+laeGnii1kbqafxyAZQc1WR48ta/y+pFbN92VKPC5KW1hs3NOD2dcAtYNylCk6yZUuudgnQ80ypORrCFH+S3SU/gGkRjn6EUlVRxFEbF689gKWkZa16QU5Ew1crMraupoT6Ny+EYSEYIIBasSQdMGzJdyXDBMtijKgrzgAbxg0GHqGgqI8fKZ4365kE/34GgtMgkXKnyjhp4/ofZzHtHa3MjiFbN+T9Pr+k63YB3VtzgQBuBhTRv6bN+5Zb6rK/2N82BzTrfRq3aN97gZuA71W0LmTvC3v9HyhzXaiTapyo/aywPTJmQrTmttWs6jTyqZMxCGK1oCEFWdaXr8ecqwvKDTv7ijm+spa7/TSWsWwCaI43sTMY+oIrcQpdQCH3W8eMtn1bUig3pTtgrQeR3k7jEQH6K91XMOYuOUX8gZFCAnFhaQCSQmaCLKGFej/sSODM2/Of+Go5t32cDu1kipZYRA0dukLw1RTdsRL9v2drZJ/RMUWa8kLQIlpNomHR5MXSs9ose9q2ytjUO865Kvci0RgW4+OBvBJwSbI2al8wM55gVAOSBECmIxDyYFpU2zQGn0Xb1qXP7FkOCSbUzwS5oBEGIvowEP95EkHXLpIMy/Hudq5lnUdHYUqiG12Ptlg5eDLClmR5vswQSAVIJDLi+9B9WXqf2u1b93YmCbviKpGWzQQKMfZVD36W7QlZYoqldeuBSIEzJlcao0NvsF34NBet0DDuPDGI6wPNNI7iq916jC1KaoKeODlCOiDqisppfHqK1uU3oO2xEDcRCUdipKEKZKtSAmphXF9qWdTHwpa0YHjfRhObntbJiWnNpDjv46uD8FcVFtwPVEhck0pxifqP7/IFc8d0Zg6YDGj0v4PBCdagevv4Dxm6ZjwtKYveM+Is/Ps5F9taRQKJp4iRer5LfcE2mkaTqh+cNiMbIfsl0fGM6gS4e5x3oyAZwOZUcGKP9eBFkRfhZotgSGlKZMXyYlWcwOFjzdCyix2xU+oqdss9JChAgCeksd+QBlME9imqaH6zoc9EG95zFpqtQP17ciibq/MZ5z5s+SqeMAQq9z7zYJDUK5jFv954kWIyWaSxaKP3fL7AdmlZGWd/K/Fo9+iOzudpyVpUV8QpPq6x5c5NEAOocWVA+F1QPqgkZeq/hbg4CVWcriJcRS9ULgoofsvnOLRSRpp7Rs5JKUqtStyfvsK/vzjktXJl72mrd6jiZIqLUNpfmIgnNh+R5GjSnogMGCWhEBoz2Pzs/CihH3XntOBsx5vcuV6pxN9VrsRQga0FCzzcs2mus4KNiFMtaTnuduwWKpPOSj5+kQJAHLmzbnu7zrvzgoZJqXBpzv1gshsDe8tN0e/eouHAFZbuxC79HZnzLa5IQYRibvqNeWoZbUmvCn2PT7nD2w376tifw5Kamri2e7tUE963PAIPT9dKqIdh9KTv7H1OOlGLg9lJniAb6rXxgYUty0rznF/J4+wc3RgM6FQABBCg9Nq3GGf2QOEGHaCf99M8bnSt9D4pW8iZXI+P/vG6UoE0/RJV6ja+PkzQP8JiTNAX2FiMaLe6xvLP04+Tu4QbMFQYCZ+ZOc+UDiy8S1npB+4sn87aJ4LUBbwoHIGfcxe92PCoIPYAdVDbtn8Sofdd0cim5uTqP7fGVf6L5sokS5sbs1OsjRpo0TXklO85oG8azbcwzJ2QKtDxDixwKn8AAELeYUSt/Cp1NHHKQ9545ZSA+qYbm6nyZHi3Uks7TJ8kq+UrnXscKvrBtYOMv3fWzHq0Vx4JAY6jEehEmfEKYCp6FGH3PTDW8dtUJ3Tau/eg0GySuZe4ZiOV98vF0arp0nRTCI7xjM6ngpUpfCuG5pjj9Ilr0vxxrfd3Wmek7mxHC7Udst1DJPJU3Ot49lJNKyf8sAxvPxQFJAQvMJ2na9Ig+oaHsFaUecBC5vUX6FuunhBeXkrOEr1B3fW7gCihHQ4u4Hl6XK7dk0wQmObjX+pVJGBO/bhtyKWEQ6T/tvFiDB1dC0H9Bx+My/k38wRRdvKQgeY7rlJdS1EUeeKB0L6/yKSDs1tR/6aM1YHnyDoS3x25cJ0xZ0v4bkpy1nMAOYvs0jVw5DYiY9/rXfdAJQOawCiXkH4kft0figv8rt14AM0eIfd6ycHwR2mBmTmQ0v/kcpBierqo29a8AS+9Lm0isxysqxlGAYY7itKuc9GVx8KTIPYsYQjtyYWiJP7irk3UpYtPR2dvUtvAhM2zaBJSMJEGNFdzG0hxoOq0P+BmGH9ZNpcEZSQIl0bJSxrVhUfivGrht5RZiLGYO38IcT29GhZqbjYftIFaQymgxVAi1GlhxJ4gTKNcREe3137lREnmVNgDWQiEMxK56EAc1lRzuvIM0YXirQ2IlYq1bUbqrf+R/WHX4RiDFO35vrM4qdo3TCx0QCj4+On3gLYL25EzReEGZb4ra6aHYM16R6skQBRwDg+JrTlBikUWBqzBFQLs91nKaBrO6npmVO75JpyZlnm+CLd4JVXgJfKiokT7eIZ83mK5qs7wzHlnkBYyIFJM9V76toclLEmwrYto/YS25xFIXP/kxkP6MTAC3h++Awnpd7hlVWMyRq0ByXE1ZQcnWD/FDFl8zhy2rgF5wJ2fll+L0jffUv/7nlzhVQvWpZ+Xh39/zcMo5KzVZ49hN6gQ32SbPxmcAWPuBxuN7hWQoYQwF2q9y8Iso4iMofIfUUbepRWv63mBZAYW3BLozOOhVpzL1pKkPteWYlxMwuO/WqRi8FFx+FUDAKfQ3G7e8e0PkqtCU3mCfwRepspUKVFJpxO+YF/J26W5pp8O1/N0GQGC1RJqRfsnJfY8z1+Nb11bw6sMXbMb0+thBtHHxdP+fFd1bjf0jMBtDTkR+ifS7Ifgt7sc49KItk0T057BfZNTfglWh1uAS/2GKiYlOmjbpBaSGyEySfl9JX83vP6uyheZgc4m8Gpek7C1TajfZow99n6H7b1YGUOJ+GP+XexFG+v1pbGGMw4PxdaHLLyVA8iEC6slyi1zAemv9FSPbFON8dh5f7maicgRuPibdflXb3wTUwkDM844syhj5jmfYOSYskkVt2rmgNDuRN50YQ0SsENiwMfJ8YA26mJqExz6AjYLx0Trb4clHA4VUMod1Al0ssObKjWylXKuFRZKuI00jWVY278SDuFDZqBNXEOfDquKDB2keZHRdmCTSyMj78BcBvYKkCOVJAdBBSuH82lZDB7Ezgv1J0qhqfmGVut15CVNHFa1dXF+l9wVbWs/TZosGl5hUvNcEyK3FVvlo3p5vWFxXbTd+kFKth0Z6tZxxiAssbWQo4FSikTTEMaSofSvQnuOto7qxZSok/+hRp4RBJWQNixIw0/JvjHCYIqaP7N7X5Jsub6luzuYpgt38r1SQkZR5Hxxylp9KVZvjnQqS8c63f8U7Au3Zovk6/LYl/pkPmfwIFuMI542f+vMxMY+owbpz+7jSmJsKqrzHx43UE0lxbSWwyd4hadvZw3l9P4EcUbEXCfWyI+sTQlZYolr15B+iA8DxGr8XWeTQsNZMJ99dUGsD21fbe2kv9aqj5ktO1EpQHu3yJcIYIKEOlytQumO9s9WrXOMSSPYD7CLPp6ZzFzAXNu6fqZuk5jXwiKYkdqYH9N+vyo7NA3lizrh1kKH5xHFbnOCwLtfWwdaWp7Ywqm6K0OWX4Y4lUd9wOsFELa0SNd6HsX2XMBIJP+ZB/N1lODRf3lyJrOCT5QmHTaJDOl5i1yV/h9EHP1hJmas753N5nLUlxWcLP/YzcYkO89qz8SADiY4cwILFlmZF20Q2TZJa/xqw/XOEQucoDFR0awVEl8TQ9GPMrZ/pJjPTWUOQzmH82OaUa4sT8kZsoRaslwPNNPFpReOsIjkS9zuBv194OQ4d+9EUnICbr3LAh92wMvuLmVQTkD8CuVjNSmzZJ1w0vzOtmebDNjMskKiAWPXRpENpWT8qNXVjGSL2C2nISFSOLwkC+W1snbo+/0JKrOXYOwDhnpU62ELQeryGNyepFo2Mt7XcbfrirlA1fOUL7MUA8/CpJVuuZL7+IeaTqktvpArU38NtpmSNPV5aAblVX5j1umJgAfO2vevaoTLm5Y4LNzwne61iAXE4QFKyFnMxoW2sKVzW1xWgt99edG7/3duyDwQTXrdGWJsl36QUlzBmJkI8z7hydMOSzhhcAC4tZVFU7qA94qLA6pfBHvulPAxhYjX4kneb3OnaraYSTTn5OuTFOs3OC/lDUpHF7ECmLv0fBtn1MaozZkLh4K9A7TiMsm+Kgv6yUoH7UmGHUZn2gMrAuAWwopWG3ZAR+qkuabQy4taYH1Xh/Mqq7Hrgzy9+bxtoVjqeKWSEQQxlSQ6NkgpuobjulGyYQuFnpMoxoNk2Hjmq/rnCN5C/n5xb/PGETJsymnggyD9Jz51z+UA/xhGqua0HbhH4jzD6ofniCcS3QBCXt3Gy1bZFrD/w1NCv95KWcQIsXJfH/dx4HLSwMYpTKBoyUYCaWAARV4sBtBtjMMzYqpo2gKKyYJ5PlCutXnm8QG1TVpCO6TZFMQn5w7ooat+beLKssspl0vbjmOX7p2TMLTCp4FoLuvkSXJrgKGj+qYAyBdC3dV3yhtiTz0QvE9L5/DahixWiCjJf03tb6nBb0tE73AueA2hyQU7y7oYZLQKYuYfDc4SLUNtHXD/25T74YmrhJsCuIpccrLJ/28HjFeibFEbyZgs6mpAgqSkgUcBQT/lvvXaQmLziNeVtuaKiato6ppuj0aDZ49+eJjJOv0wyWi+dPWSALRfpc5ftOXk2vFxm/3vsqdGXI39xQRELMZs/mAniJtdWHCuCjfaJlLJJGHg5PuQc4iI8hvSMaVMlPLfbIXmyQJQXrojQDFS5wIQSacmH41knztLIak4gCpwJb89wdsMWMQWJ9PRW84kc+/OSqoT7PQcBXHRYcdRLQuCumtuXapfXdxr95BgSgguC86p8VTkfTE40mfRZuOOlXN+SU3CSjBHSZP4tFimi+XrvAEKnfCiiDWX01H05XTntMud/32JlDouMQCxxYT5jaTobgLKnoCFiXC11+2s909LYhRqBieZBkg0Z74WtontoFnQCms4NXeFhrOaMKJY71MAc1wSkYbO2l2DvMzYUONQMl8viGbHocl8ZCW/ARqvhE8bBMI8JWv+NItcpuqkOU7aZ4BQARzQIfz0qMJym8VGTuW+9nSrAFO1gUDT8W3nKVuOblMQZyAPGPQPDXwAfR6TjUd87NZ0FicGLT+f9cATfr1f/jnBOLtCq0NP3w63RVvflXZrsYscWayBpO1aqfY8G6BeiPuJ4OSYnzpt1xhuHFdJa5xOLHKXwMlYp/EkOHwouaIV9OnBn6ZDwDc8HjEYj3Pvwk6olne+aRZSNswa1m6IVauPILblgFqR+YiW0eWPsDu6NOj+oxWQqZ8wMKYDP7MxULczV7KbM73pI9D5+N51ovuCIxBDZzZ5zsi0ska2FvAFMCym4Xc07EF/XHV15HW61ec7qKtnyBnKYOUi8VSi/g+2lYmtzLnsAZm0ehOOWXpF5Fn1U88+H/Lanj43TZi/xNZbyr4/Mz2tSQgXmzqzQ5C3f9nV139P+QemtcG5k6GyxTr5iAY52syoRcwRaRNXRV/PSpkBhvP+07FUxTYORjxOki25v5EpdDQ2QSvMad77UB3Qf1uYmS0IHL3RjKcjd2Uwwr8mq2mhP4kICHt6HbgooG3vzoNunVpBHukU/dx43B8GypX8sOGYP1OsV4vvBKvFJqtMcYvX9iq7/sSFt9OkxW8yXDml+DQ9LPBo+gQkAl+qm3w+BietfWHB4ksOEBtMzpQDMQPhaLojFszfYbEIY7ktZg/LGrUFpTm+7GlX1d4rpjqaSjnm97LZcYxf14rvbAqRrKgCKcL+J0JsuZJFsVRmnqB4o31lgs9Y2MrYqOl7Xt8W8xINUXAqe237svveDvkIDVrgS5gmZ5AoLZ+x+QGaWI/00sRXMYnOOWVLrNYLbidIRyrYG56T7biGqY0KLD+J01IgKlM9o1kFNneyj/IBUy91AAsj6y4ViwPEBYrSl2tQkPqv2LigEJWoCFPUA7DXWRuCFJT+ZkyGp9DwMu+6sAfnRP5cRYL6TVp6DqzgVpxiUMntTEaOOqSwvmibNxRTV7TrQVnZKBG7Sc7MuLxVfcDGhQ9cF4+OiWStb0onrkuuscXUSb5Vsv38iIspjW2Oa53+QzQjArfWq0ZIQRMVNmDJl8FmO4qSKza8+nTW0bmPYhi0ZFo7PtbDsPV9hILWIdWnQmvCyyK/6f0gFr20GsJACW0izD2xRXuYubb8KMq+V51oPIoEfmjlpnp0T8ZH5saNeY2kgJ+IPd3HvDrCk6eC8bee5ZJtIwQ8lqzACbIT44IRnUoLqq5WGBOueSYf5uSgox7L8TSKNlcj9eFOow/HOqEKwExJt48iRQ/3k5rSy/sCM8fb6wmAA+dZ7gxzuXfW5ds21uJ8H2DjiFMm2yX6ujNPkHezoZNkBm2wCwvR8AezOAiecweZzrrwEK82WmUebEn453kt13q6NCqVY9L2L0uNfNwdLT7l6y40KexaJktXQhU+o1u3b+pIgLEHBE7vV92foJeqk9vP1JaucQIqTpLtjjESC2nz/2TfozpStcNv5bXqw9quszL0MxhO7ubWxLFPu/36z4FIQkx+Pj2r4x98yHkfWtVmhxvaq8DyiCGfoFRTZu8VQaoFELCM5RlrXIBXpgvAJQKz+aLkZGyQI9LYO4Nr7wGD5kIZb0htQAF5E9GkviG8i6XbqpBpw6fk/t/1dQ8c8757DQq7b+CzMNSs5vsNdQuPotLvGbDBwE6ZELUmcuZv8BuUaCBmYbCFYYEzFAxEOla2Gqu4dpA0mVZB7D5n6d/yNh+HuzVKATLL9RinQ4+07X4zuszhPx7WiwIDDOKK7f4+STDJk7aZUUuORKUchvoJXPYwSCZ8e5LfdMIQOx+q3YpRWOrcYhNzGyRLNI69MNpEo5VSlw1dr/NRnxib2dOqSl9IvtAO+hZSxRSXkFyVXU0gldQQ5zO+L/GwLXdgFhaxmOABhGE5JZTPtkLFS6bnxNmm2Jv3hVM07LUWtFPTmjRpnjunYAA2Ju0uhTCfEb5/ceu2P+2fbE6vLxU+KY/m1v9p/C1ZGkVbrPk2RAsaRN49Uh57hjcoeWw7Q1pT9elGJ5xAAeVMUJHbqEFMndjMhekVxlHx0W5wk/9u1QiGsQ1VwsE73RgCVKdhbuxNroZXUtSFAcsTHukLHMBAzu2LFCA1qFKUlWGU1uziFcXOpHqeHyUjzxJFOcHYd7bok/R3HDKE/WMAn+da8+xZEN0CCFYN1IfDfCI0Bh+VK+oYpdyWq9OuDbjW0uDg63mQRb7cteoVJJ/4S3vlmJ9chdN/xzg54QLCPEKbY9R9VeEfk24mv9uxVSR93bcRa1jfoKFReQIoImv/DO2Q+cUxVas/8JbBDHiTkrbta0X5bASjAMFHG98ZODCTJlDHcLUTfffKu1MgnMXI3YMo2e3VmT6hPyf1/e9rYzyMH59ex/PhqgM0HLWUCszwU8D3XkhCltb+4ChLPMjhpHN4BymUw98+G+f0Mey4VvOxeRA3sPjX+P9nDyAke9Fjq45g3IN2wn/CjcRYHiwvl84qxT+p+oYgsNLaEp+DC8d+Gxk66AizyNdZO7TJ4SQQ1QYwUQz+GaBnHXnDeYDCMNW2ApgZH/5DXiIBAvMyGgzSDnHxYTAJJGwWaoftPWODinVlFoscxgVfi3yBvgrc7TC3tnqZIakPHNvYnWXIwwyn9UT4F5eQqK9Vt0yYmxac+dgYiZSpOwAtoPeZt4CgjwEkfRDkwIsXz1QVISoi8VbVAsBTjqGfKSNZJs+iVefVA1/dzpxmESKGEL2N8ZexOJczlq0PInSLORRXIVlt5Qekj/o7sh+loMIW49/JuNsFb28vQhlClgBgyvu7hZmoJvoT+xhyeURtfku9NqVNXdO1VoswMETEHcU2sWtsXNkhymTuO3vVFAgaamGYLgjH8uN77YYiNC4CWaI3nlV763HDmqPuDGmJgFwrzEpNk9kzYePasdE5gVuVxhX/1XUvJUasnIk6TXyJG91zVzSxFz7LsqYLfihpOl6B1cq8PyY/jpd0x6CZxJG+v6OKpGWXv5SrMvL6GeO594FYsUfvjU/aidA9YxOzBQ4LL8c5i10JC/iysiNEdzHWLWrdoXdMAW8Wm7XKvuQtf0KNESPnzl+DwccmcZ1F8csC9Xl8U7MBEoY/X7sQmK1abCH2/6trY7hhBVEI9LF5z0BWJgrbJbeIrlRMttkRmBnw6Wl9XEt+K5MPDSvIZFR486R03yZR1f6uC9Zb62e6Wp2ZgpEX8dliqmod/fjGYiBYsIvhZdGhUE8nrj5qmo4Dua4jU6Lff8npaRBD5e5ExrrXrZTJ1ynM/gfGqHZ8cgoeGRFukjtK9Bk/sLUioex3MvEfBCwxdd2WIg8BtoXy4Dw5Q/JHPbeq3Wv5S4Cd1+k5il2AqhmfFBLno3WXeu7BQyn7ULM01bYq9FauDW1qDYkjHpaODkyjAyyVw2SBKmdX+6Sx7altQP4gq/lSbhATjO6ICyqJ3peb3j3qEJlV4RRHkTAZ/RDQR6g4yB0Xyp3a2DEEoqooW2g6AfvEZ6hOvxBd/8wTztBsAMeQ1l/sF/kZeCeO5z2euLC+ot6NU/XJUXoKofg47mL4uLSqatYDE1nqvueUfSP/tI/Z4znTN7ZIolF4hom2pvlCHyRT/sNi6eP936J9MwgXUxWPMEPzzp+AOdxYQyhcTA+ca+UvvopcncVxvvrQvNbBSWAGhMj2jj26qa4I2apvHyRejiHiLAXwzbnKOzvtm3pP+BclMGWXeFzw1fh6a07xRvH5vSaL/+o1eiFpl53/Iz5mjh2tWXmpuSr8J6Z6nybc2AImTavWa+sg8AhKuMDu4hM60Wux06B8Utl+GSK9ujwErvC/7l7xhEZL3s0Rl2v+Oboeo4dBDGXsYieDWQyc9xzyTI3f6YU2LBPHtjBEWNjOEASvetqV+p2bHZcKCgurk09epY0lK+uZ1TK5h62pvMsD6UY2rrU2VDUbIlVyDJqJVe8wPfP7VdZDhf9MkEuQFkGn03F+tdoW8nCOOSk5+ROyDUlGXPYd3DpmLt9wyxLn4bRsTN8xsa40zMaOGk7yzJicujhVUym7/WNkXEiy2PfXsvdeoT7Ct9fmC2z4+aqj1Lr1tsoCzSmAQ7rgeW69387ch+or+p5Uvi4BF/+Lqm2kcBDYKRVOIZiaCO9BSYAs7SnuwnIRdnCNQiwlR22wR5+hIfhCkmWdwV+yQW4Wu2YN7Y4qlKOM2+5NzW4jbz/Cl5XrzIJTGm3U4WcC/oydIMoliD70Rpi0nFd1Mo76Ycetk92tQvr6JitAjVXU7xKmdLQdo47V6XRK+HEr9wijbd0gqULYXfaGVRqa6LbckLMMB/VWKQqz7j2q2m29nl6bHbvzXymuCXdxqMJNU27STpLI/9AvfCgl7sX27gGZWTrL1LFlYakwfmscE3nIfjhUFkoyvzl0ChnFL6noLYiRozPzvJRhgDuf6TkAtUPuwqf3cZQiG8qlyV/hIv53G8kONU3BzMLMHbJBV4IVnO+NABRqDXEPW3/jB7FkD6bG55IB4W3yotR4A6a5b94CPlZ+ZYpeilsmUq83vagLmlwoN5TEP/NHXBnTYzq7gTejNTRDzER15sAQ7YRvzhOFk7Kfy0PkaHEdtn2HZkVosNx1bzUG4Ft4/VgbDF6r+baNkkHa6gr2dEpRu3hYJ3WCngDB+OM8xHuBepIrF4dtSkmozMRYMP1NtZWU0J0mc+KAOVsWw+NoudMlfyFOI6NsNPyGCsWrf1pUMm4QkskshF5XSpfwQNYlSCR2hPMcBUkbfDMhLOwgqiEeljtwT7RwRfs3LmiGJ4dQyq/bSy9Ld86lT4ZGw1uSoEH9eRvgQUSMkFrLjQZTd2CQZMwYccphm66ZctDC3XkAml6jA1SJQNpihE4WHhPWHm0YmidjAiDeL+QUZxY8eTnEamMUFCA3mzpg7Dzeq/qrYcbA8MjVzsQHvkElFK5FBAzA0aD3a4Jh4TpouQQCNspEYeHq1tyxiaCrbKgMXqhbMqhivmRev5v2YniyizbJcmZxWXH/2UMNb2X1HuIn05YxuDJ9V8whsR/vDiAKsZypyS+Gakz4Rlc+xh5ibIZTOHex0B39STa1gWYX5S2DpkHWvQpJG2jkYjXp9mLzMtFB7HCsRLjZMqaotcXo6iweuAsryHc3GlyUxcSljuyj18sb2j8KW4vYlEIiAGrUNLzpunC6G2thTFNzKP1bEQ1mMGY1CuinHjXNe24nIcUB4ow/Hk+7QoXaoAACA17uuarnwQUPAC2aqazaS3B4uytZ1LM2b+xM9YLIzPUuugpjBpyYpXmtR9JZDl6H8L+QIWCJbXdzGNSXAbNqaOJZDD60EVUOvF2L9PfVXaYDaq8pnLT2b5tr5WjdLQZYXlcBmiSegNqt0qwtTaGu5GbQu+ZABfqRk+b7T9OPbEcyDp52og9RTw/0uw7cWl/g+Apxc2qgQCfkfoTs4OWY8udEmurjzR2C1qfueRHFZF53mAs1Po1/UrDvwzu+NoRnzCJFbg78hEV4aQqE0spX0P0/pLTZ81OIthowmDnxkqHXbwpqis3yCMgZ5Yv5iRVQxpZMQ9hr7BL5+GNCHCsMXOkoJtKV384m098LZfMiNP3VP/Ru4j6gkxShjmY5pjSfLEDh/q9/7m4NdNW8YoITd/I3EF+Bwi3163yC/ea1cKpjoH3UBZhEJKsMxvxssGD7DHZmP3enY9/Z3xpPJf/iahXHc53eM3gva3DQNWcKMw2CtFydLR+oCPLc9cDxUKFjHTtY7YBQ1G+XljgaYuRya883bw7BYvvEhkQlVqBzKArtKPqYwp8mcq8ZDcQ3nzwD9H07j+zxnrJvGZVe7NrkXtjVEQjEr1U350VZxytRYVth88RZxRlI2LdYAO9O68MVql3vyDxLzlsNM++XOkG58NpZP5XDtVfexKMJegedOZ4De6BynZxl5YyTptJSjbHWKaRLNu7YZenOG977ll8GqFUoIQCxtZdj7wDv35RyYyIvJcrcfLS2pRjRfWm3vDwKle1D6NYPq/Bexiiv0e87P2eWZbNMJyYi+jaQF6tLVSXMG6fnk/2h6H4K2BTieSi7ctmBv7CN86Dzq5ATyejuOe5MIKG14A/BuyDwcZcSJBf+BZArOBW1+98/U2L+AfobfojXHHjoKlg3aVd2E3ByfzgfS0OxSE6lRN/1ETiECB0mB1k5oVMLBloMajjhbe/RBZS9YBP+pUoU98CI8l4MM1ZgvN1YMJHq6uhMSO7RssQF3Jxob71/gdityRC4JEoho0lAGyv06qC9Pzz+SyGxaZikRql0EHesZAoqaP5Jhw+rA1QFuYKCgl1RzZQVuMdTR8c1cuOroJfbBIhZJhwAZJwcuvwzDBDKhgzgBQnRaubPiMXGc3UfgmGttz/AMOhqCI5KeiO/ZVzCPr325JUgqy3QUIO/mzC0uZvNIWPMfK9fiUXZENcVXx3DvFgONMeoePMjo2KEee//u6gccmcvKthcFDuH1p2jc+YqyznjIumzlDQjPidWTcJA8C51qa+Ae1VWDaCEwu0Gl97wAXtgPoNMJDujbI18jKlUrzKmhtqQUXuWWdEcoBgurW0c/G6k30VbdHJkXZzaz7jHY2WVmJsFil/HT4X0zy1qkfN+zhAQAJ8023A0cTmKoD3MtrcnqS9eAceOQaDxnr2M8QtHVk+FlhvWxSqIIitQ838QI6vT780MUrP4iQuTjXO3MEvCMSwKYYEiwFuVF0i9J4ualX2wGnM5EnpeoF6xuaSYB8TuXmuw715FxM8GqBixjfSNTR5chTII1gAKn+JLcm2ulQWsq57btdeUOULQj1ssf6Hgqtz+IE2dOKgcslY7YB2/7LD1lPh+jt7CXSaKC58BbkWqnpeWAao6EJkmgUp4b725eJctWhl8oCz6VB8gtxlDld8cEvQqAfVmw56PPJUVnAeOuBxCfh4dXePuuFXetfWSW/qmpy62RsBrfDrqMyBGhdFfA3FuVePOo6ztRmG9BD9aBX4or4FNRBvYg9XZ8eITNdG9nVfN3fo7fN3Ut6dSgH5a2tSF0vOjF2KtiQ8pJ1TCby93bkBX7B+d/7AtFf3qDHyu5OFEpI7DjYym/ovVWYIfdOBnRfUZxs73LzwyJP/I/25arZL1OVT4Jxwnk8HFCNkxKIcGcc3NDJxNKr0MuA2+iJAA+Tj7v1AKwamdmNUD9O8t2LIHote5fdVbWcws2SoHvDZG14ZZAhvolj1Bi08MEWMQdnBrbsE95nr7CEPbc+IqLW7BQFn5cVY6YxZ9SyMWtR5fJ2jULbtLmrsrJikJZPvsl0lvxodR7TUKs0/a1lMuW07NULT7BJSrul38M/Npm0+LmYvEjySZLDoHqVXlQl2K+HVssl0BqSzKowdLNGWCcShZEa4K6rp+FQJXJsXhzbuie8KpM+xZWCB6FuILxI+3/LJmYnRcmSYRZOWQETZ8oxQSflrs4X5SnzQANpCmozEqZQf8mcKdDSOryDUQFKXQHh0fzFv5nKjyNr+W6wZDr/GfgRKIsVUoSz96XV4n3sN0kkVhn7+YA6iIhYJJfJXRdiLvPUg6h25onVMNiNQfWYTfgbp3UgDytZgaA+nLBbXhVgAuZUuG6MHyRGsgs8fFnSA2YtV3sTXim71CT3Mm9Z35FNSHh6mkZOzL9wKyagnvxc3O/USG2Mik/k0Qu00fssx1+pQhVaITAKjW1DkMW1m3BbRbHhgMeTs+Q/Rjf/E0tZH5Y2K93NmvCsSi2ChC8GmdzHpASqSVWLNHua09N49EgzBVpxNmKqzjEBHQxkIK8I38rCVTqBFSbyA4W7/cayt/7EvXeZztMWh13NWmfChRHUtqCMAHXG6XivxDln9xQkm9En4NhPRgtVMJcRhiFV866KQP0iEL/Gk4J8ftDma9Gc1HDI1IaBKhAb7lkPIV4se3akB2tV2WVHj9QNAaDP9qeA/IcDqxWwXY00MjnwMapthmsrKtNhJt4kUd5/7a8zqLplWJPxuY4myAUd/SvCegusMQsehXshyFg8jBAUFIXbxDIpV6zx1fffNrtfl8d+s7BZsoy4h392FRB4gjSMFW8y22KBruNtHAUS0zgQzxNZRRoN27yr22iylFpEZ3JOo6/UsclLq/RdgEiyLKwwLfTfGPoS+4FENu+1c2c0eV5YVnII+XtjkhwfaZi9lZo0dwZegeQK8uGGTHIokkINqAmdOohx1zK6K+70lmQwRFmaWWMhlEQI1jy34tBUx8CaYc6Fg0ChOfq3UgB2ndlVuGjen6sNA8iqz8/M5vahaLztz3wFOpS3gXkON5Fgv6CbOmCv6wEdCKo3QEGhLTyN0T6DJlUwg52czjLWYC/d5fwZa4RVJVNtTZ9U3vHp4FTrlOBADpZiBXp/ckVsvHqdvgbprNZG/qFTGYF4+Ef+ISy1Cba1bhlpFbcliMWHrnmY/pJiYqgehBSu1fZjpm0YiUWFi8e/yAgcR4Ch+ahRXFl36izclDSHfrpeMOJ2c9GN9ZS8ZVUqvEdecyi9lb9dFYG0e0zPYVKLQuhpC+fxzYdha1cfK7yZNR9RtCIItoq68L4jzy6/Bdp8LJzCA+867tuPXhsshCFoZYcIu4TOJMW9qrppTSRgiAZziic1CWFDbsSHLDGRn9Ud13H/71IeNLirDHGI04eO4XCZrJ7KnIRKSNeGfV9yvokfxxvRkjj0hUrFXvyfWMrIHhYJ7ZbSUBVSjU2wnyH35hZdF+JpV+wRnvnd1ZovhrpXClbwEkxuSKQwzOlIJj9QoeYF7gVtg/6gDG9PjaYSAPtvEF8AqTE2ok6lcyiEF4k146dkvnmeykwQHHN7IeSaifSdGBtY3mcD/u6mDXCbe8wtulHbvdtTd30i+DW6I57crPUn9/+xas9vvUuqRKPq9W5MmlQMBcEtKmUVmepofo8XFmIv9OOdNoYpCkPLYqE3X7MNH+12msWh5mEMHMoIUvNRMiTyV9xJel0ipaP/wFPx2RmtNGIS6Qozac5BAQCgrC02FkLl1NKmKSlXNQKELR0KMejelWHAgmgTVE/fqlyVE8N8gkCLdyiXyXNTkFPK8NrrBqXl8RgON660A4eMrFY7jRlKwbnNdoc2dsUHs6y4Q8fL+RboS38TPweSyowyP0A0eFzhh8C+gYQAgFzW9f7N2JlGu6uf8z+hnioAty20EDS62OhU1VcwX6XFrFFtStUKT20T8SOJWdh7EUP8t3jiRgyLG3Jo9x4rJc2CDa1MVOkzJt8g3btSSUpoucBwzuenj9SbDokVjA2T5pYHXMiguGJhXh3dHUOb95yGvK42G8MqRHc+Ky3suHNp4HM7bpWylHmNQkTeNjm1ttqWPLrKbD7rIWchl7BQXksAl2rKO+r0urESooDLIakb/CUxfoNJuG/K0i1h7ex+mt6QaHQ6MZ8wiaCAT1zy7XQU8vsrX0/J4DotBpbM0uzbKYmA4CTqGZ/3kOTm0ZhSDweZEgSicqVvg6KRCrTSOrcD9W4VwH8vZvbvPTwTw6boo/m5NPNsKN77/4apb245ldbOcKUtuYXUn0u38f3s2+eDXpNcHb7Ht1yh1xTsSv6QmyMiqt/AvcXn4I9DlmHr6OqRwl64BIC00YAZ3OwB+wpSanUxaHM9qJzn74LYS7Hwsj8uxCb1kXpKdFuIx3LUFcxx1ipPZAjAgmVF3iZiaV8uYrRO8TDx0mCVPd5jbrmZ1qmRis3VAxbbWR3RLOtjl0Edxr/CqvXyws3r5YWg4dm7LwkcTcmedV3tvNBuM+E+itft3oN47ANAy0jveYsPVsEolHjjPb5GcnU3tH7wrY/8DB9p709m+QJpqTEd6DplScR6h8LKldefO6Mit59SgWQG+ABnVSZO8BNcIT3sMWmGCEmAeLenAOwczUAWe9aMhZBr06D/icc3ygKLzJzvO06d7Cgee5oHR7z43n7Hl7EgPWKQLbBw46/OknEsubP+veBYbB6wKDhd/5p01IN67K2T73msV86uPKqDwRzrpdjjAa8O3PVhMwrbU675wGEdReEvelhrs1sZmIvDBs18a/YjbfSY3lZt5Pzyjc8WPMFHJEdAGmUqEIt7cn82H8c5oaAFckDh1t37h6qUtGq+DsYs36YCqECLZW85kdXG209FxDu0nI4T1XNNEHHxM3Y9Rx66yQEipHZC1AVJW4MGRkqZzIoMs0gR71FgPrA3p5lyN+rQOidUDjBrmXj6Zgd6Onyy6ZHcrSlinlP/0nC12HsFTGK5+PROBtXXs0av3Hp48GDtY7qrZqXxmlDaseE44NLmkM3eT0IhVazFPu0/FTGJ+tdPc45k9YLnrK0oIoPdgJoV8ot2tzp0wP7Bd2mfXj4L0rQBd686AArdi87BtppCyrvBwefTaTlSXWDT+RJkSwIeEoonKzUdHqIV/9kFpvBz4w9yzJ1XXOCjpXGkUTQzMkZwJ9PXmxaFDWmUtSHzSK3L3LjKZmvXLK2/+44tFQZWZloVkAclQwm98CA0zbRjH0tltMZnPq2Iw7pOCs39m7IeFJvxtx2mo3JQVDezTfODqXaGc8W9jmV5PzLJBUGFc+bG95QRilufLj9CoJlFnWK9xK1pvjUyILj/FVMDnzzjMN7SEv4LMuUq9QRhLb5S+COykFFWLkhgJcOM4R/9xC9vZtZ01cXBBTn/SfyhcHjsItmQ9HQ626r6LVb3g2pt7pSpRUz4g3pXFxz88q3BGcXu8rAgv4A2JIzADH5BuUK0OCGRe6ouxkxcX9icsHOGpy53nFcd/2WqS3Nstl6h4Uc+4oRcmqvvFqMl6HZi7GUn16w/z0AYCXcTyi4UsajRxVaVtMJYsmD/IcVf+yeoe7MMoBaVaxLzJdM6iVdSfUB4gnZjXvAqSayk8ur8Gxr54FY2jQqAZZH8Pd1DKvL/4l+XcJZTOpIwfHaHae+b4BGLh9vQ0i4+knQR4Y8+WjmbEhkrjo/HriYUPW1CqAumM+gdbjO7CUVHXrWJsmgRGP+bjPtq/3ZQ4ZkUfMeFie3vqCJJNrnGNKm9FB3mGSLDzZbokd2W3iXvm384kVyD4XBqBUQGCZPBezH0McFY+p+7l/7RH83hmMLWeRgnbaR4OC497xaerfuk3xM9JZIIjbeHkz/lYlElk+Bt2VIozJulv1sQSa1Dpi3RkY/OC1nOc+DwWPw1OLgAYvpsq6XTmXoFrKo3WE9Ud47Rn8afWCG/HwI37l6OqjS4XnS1PK6Tl2OMfITni+rpMmraQxk9VKYKL8L8+P8f33dFs5UqWUybHJu1tmn+a+pSXJwORxPPA6CQWnwauazupSNS2jlhKbmJ+//nNQO2zzszoA0O5r6gwsrR2h+ElGzJjAKcPvagGdvN2CDGy0sUYDkHWekEwWUFXc+7/Pvae8Jj4VXvV0boFPi9dv9Zzr6ENFyFtksNtNZfxbgXhJ9Qeoewf78DnzY6jnV4k4BJ3wgwoyzgpKhYPSjLiCOOnV7qajCIdDvLjzSu6KDf9WOri6RY9vpA3hi2H5lb8mLjjf5kB3U/xCq4zZZD20WPG7s86Lu8wHEHTL1ZU8HWkWNfc80ucVrmEzPEhX08yG9YLXoRtCJsu2DF2/6dr1EE2zOQUvFWzaS2+hd7t5gOcM3laTUt4rSzQxQudjC3X6P9O6kt8qVtq/Iu4JJupfGW6QQeNyj7+Mseh5lApKhLY3Juwz0Ra1sfW2GKTJjKLFtxNCcUA37/oLAXKd4JTh2+z1LFiMTr5rzAsXR1A18ZDcIcJmoE2w80t6ZZIz/xEmCq49mKBbF7HnSK4bB1zx8FSNV5IGJjlwrN57FThYqtKOmiOZqU00+W/MPHYMRNube9Q27hNAUa/EB/P8ZMbUza+aoVg/ZJNcNTJOWzEEhSwe9OQ9kAMigdDnv60rXj3Y8dAukkOGLiom0twm6m0+edjaqJOOSksiapXFb1Nb8UAL2MbWOwgzC3LUY52sstqbYm3e22h+6+Z2+F86g+GDsYJG2qBI3tGuzqFIh2FxqSqDZhgP/9/nW8vE/ZytJBIAYy54DMoDkP0LtdO1coERnvH9bJH4pov3DaNAM/FQVfnP0Di16BKIs3dg5LNar6/jaFdMZnKcDSWXpOIIpAR/cZ94uDwJXgZq7z51vOCdMKAJBUUwEGc5MOZcy+PxU7TaoPWLFs6Eheq5ZWsp2Z2FwUT89S0P+mCLDXnWXqWpBzZFm9qN7RVGoAfWmQrlheE7QQwKYdEi1tZ9rGsmzk1OC0bSzoUq5AdF5a4818gXNZQA1sumzr1HeBg20MiOWy2U1uwJOnW8d4vz/m+cQsScaVrpZw/w4SjAM1nY169W5dIFfmH1VoxlGYEiu2DYR3vsyYfe8p40dJ7V5a40+/8jzQLTW5+KGtrVJJKwLmpHgpaKwh8qKdbY83DQ8iCYn5S/fq5K4OLshKSV4JjR++UXGFpPcMRCqlQtNGMcFk6CAn84bnLWycM2KiR/vKmKOxR1fb1DYxm5V1PXI5bq43JacGwEXoqXQ6qpiciwraTUugYNmr2264FP65r4T+9blFC3WBaM6Dx94DBVYGulXLpbvtbiB+fvmRUmvqrCmjeXfhv9RAPqJmL9ZH326JEpgQN1YCvi/EWo38VvCFgqbm4pGCIuZss6t666xwTvcGHXjHbPLKVQ+PlBO+1nbqa5wBx20jR5P8mkN/Z31Mb1/NBBLcTdRtYgrjP98LTFcaAaXz5xRiH+62xSPhhgOUQRzQV/i3y2byvL6/vLNisIMSy+8OPS+exofc32iEItJVSJAp8G2ReIOLY+d7ZrldUzfUPqlCxWEm4ClU7GiBaDI8rAhnZsRpjpU4r3nvMgGwQMRlTLq1bNbG3TV0ATiulnogXij5RbQ3BvjaK2D3ctDWlT+CgaLYOLoOiu7zbI/zCHlAGe3jUJnWO6nDqbWwE/7X6xc9kiQvUKcm134IzIOCea1KtZXd3386zNlOYrkYoVarv96PkjlSDPhVFRAf51Z/ZEnlddhGNiQQg9VGr0HkC5/v62usLjgJWYB8TmpMteV7wnJfbSCyFEn1dLQCGGFHjNMg5yVhs99mTyWGDfGq6rRneTk5eFRBq0WqkX/sAIbBdcezvnDXRLSelyDWknGRNnC+7i4RjmU4CORfFC0qaJpRXb9yW4j/gdmq8XLokkuXKwZNZuZugPN0a5ARHyl3MSiuuUg1zGLmN6MTJGqC+Jl5gt/esv22wH+kxgp2oARhJVBNsSlZA5qGNB+j6aXIxevJsU5r4yCeyCsfxKozdYoEiQmFmiQkWwM3AXRrJgKL+EbPBB7UVG94u4XXrv7dQ52JwcKhu8VHD7HgQ+SJl4kah2Wn6nuxeiE7hq7XbuzyyYa0lkAOYKO6EHKm3egHXK1dWSsxlj+RdzJFGCbGkEZBq43T5y54sBuJbk9JT6hTSexG2im4gF/lH6swwy/l0MMryKW/RES7oZ+n8ftS1m/AFhkZw93QHG1R938FkvyxqoVIkJ3bTVeivew6zQXsJ0pT7xhV4P+7IRCwu70dnM9G0PV/obhlQQkOywj6dR7qK0v3+KAnDi72p5m5JcUD2841IqctAwkujrRCWuaQBkZH+thLgjTXejzMNDeyToPgYlbUZY1P+bLPze2tDC4LiqvTHGamAY9yF2AUXPNKhbYPWHPHCkTaYSUXIGGP02CIjzHmKJDyUisnZ0QwKVdynxjrZ05fnlbSsnrC1fzvNoFMSiV21I4gaY8y6Py2CfFCqhQPhnlbk5Rg2tMhczF65M4i1rlF1WBm2lyTFb+avrYMHA/xxX1fnto6sM4onQXBO6G+zsIY1p7niT4YCtIVxF6LNPfxOuU9BHALQr/nHc2EH9H9iLVBruoDdskr1+0mQjQ3MpTY3pmB/R1rqqYF88X5H90fhpRXQmkp8HsyHYY8VHNl1wOCqe86/j5B92WJpM2uJ5Wza4BLyfnqe43VfSLeiv5OKdYwP8LgL2e2IQC/LmihaGFmU05Y4RboI3mymU+64PpMKCRFWvBxlhhU9+/Jst6zpWf9xfB8b4wXNq3Siti7oJceRwWZoXXkdTbGL+sn7pQPJKu1A62m9j5GW5IlCKMq7hwoM+iry+KuTTd/b1o0tZB8CPa80mSH6R4pd/ibRjow1YAKahQqgUOGZ55bWZnPWIa7EYnlTnF1Jsz5lFk25teZ9SPzTIQVIeH7gbGlKPOIcuzvA4hNRYIWGK6HUDm8Q3DjIBnuGUliAWuivpWTDTxXuHHzl8yoID07Xccz2Z5nBROnhnaewroUtAsxhMvSs2EoWh4j7viywRQC1+Ve9dQN9lSsaYqSpaZnR4kAZNHxXftDpFCrF+poVvI5N/wa9kgKiskJdHKkaGDOsuPFF/xRdWlUZl58x5Fau+yhyxFyLCsZFscV6kBAQvIshPwdtJ30iW6b9mqfz4wyJouUvtCn7o2PhtEsVT9vuWsTwDnCwCUKyekmxgLLGNewgw3cVnG+DsbVCIDaPFdFV2FKWSKJ0TyxOMYinFVONAYpW9BI3sESWg3/Sj0Upbc+HMjrl2aCWMHeItwxr40jBtmU3GvJ5oDeNTfuNcH/ZR3ThNTHwHDRpSBIKjX3GHuHucoLor9ybx3x6/VuMBraRG4oeeohFUcm+obbQ4lPiBZhhSjSPCxRXrwq2cTT/1DdcARAKHhwF/YdASu5QweBGdewZxoGecSW6iYF6nU/oPiewtb+PGRCubBNQ1n8B9+p+pkw8k2RfUZ5W+wCAOFOwY5zG7qMNx9EjB4157yz/iUXj9+JuS3qmMuTq5AIqPSJxL8tYmR/dI4Cf1ZcI7LQiKbwhcphJqGkW0SmRs7nq/7Idwm7voxTQ+/EpjeuReGrfI/XgNEut9it2aQ/aeZDzOcC9qVT1/ZN81qFrTehsWyrRdL9nmK/utQhvyaMQysI5DhwQpI/P8aLh09F4zoLV5Gba+/2i5xktpUnXLNHLLksXJehIW0yNaYOYeCmtSqPQ+p3nK56nqX6fR4yNrrnf5ONViNT16XUOBBG7USiz92NST6gkZa2BJeh+EJKbKZeFKE5ANTDMcYaZb/ESG2Fyy51cLL49guFOsUd8AnmhboeciAP+G/U8/S4F075rStqU+w2SwMk0F6XtL/+3JVq7jUcSNCnfDqFg2VLOCaVSx/+MRm1ilBIKc45CYnIVP+aIhGnuxig8pZiYuJMDCgPt4g8FuFouT9EQlMjvd2fbrpkX4v+dqa6TmMATbwVxgniuus0Jk+k26MDeNVGWlOwDcouZe9fm9av8GLJjY0admfsCt6SZp8Nr7cKOtIC1YAAjLE0Gqr2PPl44g+9IbkRorKrQWDIHztDZEV4yDsz8q38gHF/w2cVeoK1TJkE8c2c5P5Cb40FSHQdVIY1uuEp5XNK2XZCWRUBW4zhpFMQsp8mrgy8BSfBpLxNsfJB44wnyFzwglNu1EXutZHOMdd/u+WV1LZF0abx2ZnwbE2GfMdyHA/qOX8XsOnBLWL+ZtacCHQXWYSo9sfrep6a6PNKsq3elUlDuvJcbMMKL7V2/KbkKVbdSkqdcleGoJHKzi1WwRwMFC8uvaGcaCVqZGOibtL1v1hD6abaqgE9rmZkS8DU5rKqGhRu6T+2Hm74r8oIDPuvbfyuSz8WTHI7tW9aPBn+KMJ7FoxNSFIYXwTmO7q5GN3ftQUeGCCQnq3vOegD5XLyUJ+V7rirjU8opFsnGPrRG09rAWxoX8N0YUJw5CLHvJKDmtEqGjiIBOjECKnhOI+xlg6uGACQbwN/plbryiZf5ew5xc9IDgE1ZekypREdKT6kuLuBy9h4XMFXaahlXYb8+0O9hKR2N2q85WVJYAowjejWVVfLRRtRCOAFUA7eCdlZJp1Pp1C8VGaD4sG2XX4IKz4Dv8Ikg3hFDhz0OBIBUKaS6qrR8xicc2MkWxd1vSI0nN6eJdpMPRw2iwDlI90KV0zM59+HJsJWvmkwH2nfB47Du/aOqmAenZdMP+gp54dvwt9119JB/1kWrhsXw8sPcttlF5idnQbTrKCE+GDmze0etpKCmIHRAkFSz4TyrrByJ9Q+cOVGHPlXv3bQE+rwHSVy0sRhjbElzdZzeQIq/Te82wSYC7CJckexUieXfwmo2q0V9z7/pU9gBPyQ1KcThnYPme11x4DekthlohqNSOhz8Wdpy3LZ2aTMFc9xUUIU/S8zIAs+YY3RJIXJ9+BYyNPCZvUmPzXD35AaZHCYyLp7hoHq7WzDvIMulqILfX6zMY0omU+aQsitudY5OmPgoChdacZn0+eZzlYm81L082Z9MK9Bix3GgXH8HU7plWah0OtfjvIjq6i9OqWiXDu+8VP4fI8tRgQirexkhRq0gsHvujl8eHs7UMH4gpJkGRKZMiPSwUU1iiAz8nAar5IzUfLsreM1Y31do7RMyzdMCbUceeshACBH/stQPPAXrKDnpWrrfMZETHBZpLAv1utsuW93z5P8uolRFn+KQJ25OShFgaoZ0D+m/IQxKFrLKmgUJ95xJJnK7DiCV8FCB1G+SguAV8v0So9+N+AZ1Wxy0SxCgsei4WAOV2E7/dDyecdRthdv86jPTUJbAnr/Uh1MKKJbKHxtKft4EaB4Uzb6mzmjExCkalmqnaxmzxfGFOTRs4GMvaMxNgcMB+aAVIAwzMzNe1VuUrS3Yq0FOFDs7lO8ed7/thU0gOj6ABV+7MShkX/bbJ13c1foHyjbeWrlqEbZ/sqm9u2B0hWnW7aH/wXv3mPAp3uQ7JEcdjoYNPJgZzLkXNwhB15BxZs6mtVNHklVz8ktH3hDCYlusp5sN3H+nX2uSM/flmnq9rIcDmAjfMiJr7pvzFF+186uB4nHtWGrWtirCCUkO3C3YAFUWV8gHrgbTPIGWw04IlePrJ70QBkfBCmr8GuzlJziKuK5XyqCYmFjqj+sfvu4W3fcbvm6bO21vnweVCZBOBp9ooUe0Pno0trP1GEM0cIAytPG7vt8gSifH/AaD3Gf0vtnye7VvFTYjxwqqt3F4f/46oGhd7wmiZ2Z0C243pBHf0/B8+ztfy9pDeB433uZEr0nLNO/myxlsbVjT4Kj5BwZzjpnR+3c891rca7jlZF2YTPSmgjblS4FStef20hbp5qVbEgvLxspX8+wXjcLTlmNvjQSpdbBnahmiOnCjkQfbZdXhcletJA9+vbnqetBIDmnpYrwKpuKw+DRzILCYJOHMKpVizlDvTG0szAjKL7gLaU3GqJIp4yEHCwjlnyoABMTzQXrN46GT7WSFfZsLEyURO/6Epcb9NGecuWtRJOsyzcV+PJllz31TUtgtrXH8lN8OOVHD/8ApB3CkCxtSSy7n6EfiHHIDQ5hlCgE7T8B503oU8etIPgSAWJemx32f9sFMD5AsPnkx3vXQeC4sk33EQQj8JIz5GeAmkhMJvCXe341U9aGB6ODKujIZpuVcfPWBdN2n40F30rPWMPqLO5gustga3XEb6ygRoMyUFkKJHlQlDmIFozA0NvIo5O9GHm2JM+UgYthrqEpPSIvtrcNep6oHaFFJ5UVheAoLiLTf9z9hMC7CNu2RT56bfqexUcQiEESgonyeh3BwAP4/5xE6dABI6u/6Due22GpUEfFasgqCB2lHUB6X9O7M97u1bU7pPsIu10AQDM49AO6u73P7A1v8Y+sQNXfmiXbiAB4B+c3o519kcHGe7xjH31eEU7BuIoEIE56Xf3svzW5i9LiREfaxHgSS22225mhG1CL+EMuIDGbQ57s/O1UU7hGrvycbznGZgc2lfDdcivx6MBDyNyUR2ZO7Rph9TSOMDuNoCV+AT1x22bK34dEYn/fSjl7VC15b0BfJsmHHFKBxe27jlCMUCEi5V0oUvaJsKkyfJRXy0j2pVK+cHGmgSKQQEG8bKW3lYFyt7U8+Jn2fM6pLzFQ34rZZBIu0bQGYTba1bsatF/QopjEJi5l3vj6RvB6bC0wfi8K5xwe9XyzdEEbt66hvpXIzyzaOU6btzJ2dPmfzlKyZ8okoumtNXFmJQYQAyCQN6UJDOSbQ6AT5JUibverrHtj1yiljlcvqIHK6hmZKTgSRbsrUSMoQzG6q2k/X2YmsXflyrm8c3aD/v0w2dmmrS3LUBHd/kI5jjFW0VwJNGEp1xwRkMP9HdXybehdCga+l88HHPk2muZuj5qSKk3WUiArnxxrOQpjvZfuy3zCPgPJh0ctpcljvgZPQCeVipOAzc+B/52HO52D01sKB2QlXx3GKH8/5LDSuL6mjnk1mrSwBpbDc1Ef4+Jd11mqd+/xt/tUHiW0pqLzwi7e/fCNeYBMIvVJL4aIgBtgrEN4+VMNM3xv/nGVFRaXZQNcrWQwXYP4g3MLSffPvm+SJryZzp3Nv3P/Ln0v9LBO8/572pcKjWrRvNBMdkhAkXHNLnnGBukU/IvI709veEVsqsQqLXs49p2rAzbEQaPp8AyWwuya1yVr44wnmL57I8m1GrFSst0+21JeVKz6HYpqXTKrOCjDdFerVx6HaIlw1QmuNxnnEjiQwRQ+NWDaJcdoiATSBziu+3jXDxII+m2MST7duRs8KREo0hfUWqdomOzwEtZcZE3utHs2bFMoWVDut+U5hShBReYfhOSOvmOw+sgLHJh2em5HeujfEuObw/yk7fIwOC9ekZ96ghndJcp0hYjNOPyPh/OgQ7mieZXpXP8IBI+7KbzyvERt7E9lqwNNKCziCM9RZjkT0YtItpV+OsFZjDApq3+Esfc2lrp7N1R9oTOPmuvUHVSGnA00yfm2VPDsRTHkpdx43v4GteRfXeR0EA0fMXU2IiGo2CImzL84dNguVjvhUZpthK2GRzs4zQHhl5bsaMQ4/J2HD9ny8mVK+YsK5gA8hy07pGLB9hnczPX1M+Cx1MJzG33nnR5QeGPgQtYrD2QIIQ/651y7j8GFKpKPJAktPWSj+gTjRrRZ4cLQJbZ3LDrWTJpxEjn00FSVe+Kw5Z9uBPILSn0YW/PFvN+w9kjz5aeHG2gjqDfgAXi8efK8IsyoWs976rSOP5BimW51IzIIuI2XVnddBWf1N113zbExpgYkZrizfawbwtr0ls8kOoorL85F9U0xdeh+q8iTOMTPljT1TEt36/ayC7vjoMuiMarCIKqWlLaiD9+E3mtYYPYHt+knm5LLD8HN8a1Wb+PZFzDJHef5DtXDwPUfS6CPldo1OXGLw/wHijn/gAciu26nJU+OVH3J0fXcYEFY7GSqH5OoCux9v55SO4aXMPX4mvZPrchDUp+AVgYhlwVW5cLWkMfwTZ2iaFmd68gu+8BhaQ/UpirX+Aw1Fs9f+1bIAe6SWWhMRUuzCKlcY9/T55Q/i13ntPbOLElzrZWBqq6moK9A+mLeK3gpUNjY3SrS5rU16XxdSKwAW7udKerylQCs3u/oS6y27z/J4cKnLeDIOBMcAezV+GeX1Wx1GJP+RcXpx3bgPI/UNxegSw+4ZIY3SgwNV/MJaLSoU1fYnSPNcfyurkf+9pZ7xKrVphDL9gaXZRhfZI/BVTTF9qcQzR9Pu4dFgaPVJVu2ojNx0v9ewPXMmq9pDz4dO6UrMUGWpjfNmJF6Rl5Oo59dWudbgXa4LDv1QTT3SK597X4pjLgAk/fQxHGffNbB/B7i2SAe2fSMW5JVKj7Lpddv/lcia2vCdNongGEhfeCPGBB3TB5WkbJZFU2KRopvASnd23kxiDiN4KnsMlHuuJ5FisaZ6CUEmLzgXIHCmqIk3wUX2lAlvTPD45UwQkSzvciFJeoEbOTUMLTAavTB6E5kmvDZvuOJFM8FXx0GxFX0M6U7wtgWHGljUbX6/JSAE5O3Kjxw6AHPhwLhkaNJxU2fMIUxfgt9Fr9VYqhd9MRVR+IAVFixcbn5nr6jejOzposS6BhaAtwzBK9IHtt4s0cZ9Yb365+uSGZiFQrwL9vLHdfmKjs3qw1ythKFz5irSptigqu65BJbTzrGZRvZbCFEy5d2APGc2Rr3juh2hleKixKc/SY/CX26odruP/H2IyMCHF8ls8SG3LTAg/mhpxIFsSJ5mumjmIWaZsUEPWz33BRmsL6GG0mB5hkMSIfNVefLaof8J5pdbDcdIXJyDBrdbslKeKLCdA/OfKk/tkp+uH0qnARPMmZyvpMhqrIs3rYK8AdJdRZa6q0S/ttnk3WcLLGfJ4ZYXe6/ZOWXRKBQhWXrWxDVQb83Vs/NTLU/zZo4GMpkW0N1We23yONWU+V+IE1vwM6h5o78sC2/9jBhTKk1lcYis+7in6KwEaEItT4UjHsuDRczuDdtpTv9lhzTF2pyg0IVT2F2xAcyksllcIljFG14LxbtM5as/hq5J3e5IKf1F8WWhWPsMi6NzPZGi96E9SgXiS+nLgRYxvKBF5X4Zqx+LZBoImWZEFPf/A4Wow8W3FWoSv+iqD3XJP6ydhQZlNyF+JVFQagEHGy0KXkYi8VAPur4Jzs6VeTR6HOaGNE23Co6J/NAQw+P4+moF56WYTgJTxpJu2u4wMxSCbNQD5/1zpd/s9yNCV/ndSiVr95tcvy1R0WXLcUsO0U1hItkiauIy7iOOQ0s++O+ecwOzf06F7sgz8AsXJEPtk7VxDog+gBG+f9gaAZbZheIdY3fKb4eePQzHRHt59ExHieaUMR2EvsKQ86vticIqVQCYUjoaK9PcCf6EzDy3e06+P1CPC9hhs8CVgz++E30GYhF2dR6IWiWvr6QGQWKjS9nWRlQC1tgEHqBHl0CXx1FNWLzLpyLPSdtXUxbK+ui1J5vTr9ufAIeyaldvoUoc51ZF4Hr/lSpavu1N77XlRwici3bpU1uLNHw+5dsW95kPMAOU1CO1Eg/7mAG33h6rPFNlejx0seYArmKjUdbmSQbM6vP47Yp8eWmnVh111uIP5Ka79wHqHIHIT5uEm62jjdnW36z00c4w2l0fr/wqmabcZlBQ25489mD5YGGVgkLy7c+zSk8D/l76YoW0E4QSH7UOSuk6TCWejxW1nb2l6mF1cbQlKdIUFNi42SY5XF1mkSH23ncyiWVFdNaIMcywKIE9bTlfao5i7cxdWLp3SMSlHKokW/uF3ZiVm46EUPMhcl8/tijUD7DcWIL2rHWHufNuSj/Yv90eCaUk3ISiCwVa8y8rQ0ZU6eq56QlhsSennzbAmUHujxjfS9G8mveVCkCa5tEJ38etChD9akgAq61bTuMJr1us+NP9P7dU3c6Ijj58lZUkP0uvLHZtrMEjLob2rBKc/CNTOX1v7wbJtyudMIi2CdHp12vc0MQhHocgaFRtqjoPtOKiuaLAH8szxuoxPNvVq/DBGUw+M5knCRLIZMm2fcbQ1RBV/yOOcN3M6/AyjlGFk+Ompkwh64hPw43iQbBtuTAiSfzeVg+ku8HqFLIKjEmeHh1ACQENi2bqy5eQaLgZ3SMUQOQh4SzzFZHcbdK8vAgJ1Tv8wbNCrP9NNnxxWjfjLyaMe0gvrvRHRSZSUnd5xVq8USSYMb7ZIJ3Au+TXM5QvmyTkwYwPKjDfJ7CHl3vk7Mwlbgq6tFNSqQ3hqHf7nSjBRXPsmV2ab8dWnCEVVILhSpyzHkGxIZu4CbIM4UGl1Nl8p6gZQNLbKfeuInnHnPcx80QBHp0tIYQ9G5PBGkJKYYq9QkMWhNqvJDSnPc9ov+erHh2xdMBJiNU31T3KcE0lRqLWRjY2TYGWIfkyi/5gdnaktJA6nuw68nkd8tONR99bYMB+LUM39hsis1EVI98LWMjLe7vI82WpQVwd5PsECOUh3gPznpfgdxbG+feH/J8opxO8YeT2kllOV+xtyH8yWAkjAzvoAFLZSHcMG/NpPo9shvsNU5aNUk1FGTnwcNtibUR6izIvdebrNoE/LLV0Y1Ohp7h8FZ2CekG07pvngv1GcjFbVhSoPtnITDv6ViKxAqScDbhSvJuT/w1d48TjZ7JVQYGZRMmkpSJTtxh5lpWbyUWR1o57kT7bfzM6ZRNWPhrPT/WkOSae5f7uIdnPOzqBO6w5sDBFb/SloR/uQb/qemRgiy69Trl/0t9L2v9lmbXcjGM838pYBT1dJT1TnkNjIsJpWSp81EHP8Gfl0WSTv2MGQRh1SSPsVpLqlul7aU46MZ1fIrlR6KM3nEwWNGcB2NElisfWruYNaPBxpL2X7+IFHD5j3y+BmlfZP9oPX1Z26c8ZdI/H1ZTaA+Hc7Qtupd7qHulsm7Dnyxol4jJM3+lz4DbvtFWVmMPy/fjYiliCTnPTiK3fJY/WOVZv3gGY3Uk4x9Vf5ql6gTV5hTkKzsUdscLoOYzjwXnkAC2L0/WZY+B2ZOgZWgmG4oFU4VLau9JC1uouDDwp0CRNsdr0KYevcXp1pcpuJIxDQo1JeY/aFPE+2otR0cdgPo3qWOGrS7KJFnW0TZZoZ+HRs7H1m8EooVO14rVavKJoTj6PxjTdnQzR10Bf3clA5EpiRaPq8aKM7GjemqrTYUgnGnfBLJc4wNKjIHWTeVmWqPMyHh/hyXTeXh4tyTV1ZW+dHTpjN//fjvdUpMn/tYEzFT/xn+GeVJI7FUkBM9PDOYiM0ZXCEV++8FY3QxvOJWodJQkSRKDcXVfJSzMaxkiw/oTVZKqD3rr6CZD1UABZgGlnveSTF0HwtFQWY+SYotJwmiVFa72SZBCbxd0JM206nC+AIQDUKCO/bPRxXK/SpWv+RoMxRLD1IK6jogh2WL8l3Mjbwr43cEBFUd4367I3Qyc7p/YfywyMQ68fYORBv2Iqg58qOzhRYZpfY2uqc7B6FLrcHQr3L65SmzNU2JHeEFpiKwFKiWkuf5UmXu+9DEYhZBtZMTzKx/hP94WgJucpyXPw/3hM9VcB7TWaunT8vwJrtQb10x3m5FFbLGFrVshtR2NIN0+JBF0olMpvA8hJLqy7hj9tbgva3n7qvTTAvcnys/I5ft1ky1PEJL/B6OSosY8OaMf6P4nDQANxbhYH0KLFd9DMGudjt14GXPXpgvO52SuMIUgnl1KQihtcwKnbF0KQ4+cpYfaJ/Rf725kV/3BLAOk334rjFWJsuEDX8RrvhLDx3ZV1iLMzVpTybjZ8t+HKxUNTf++IX3zHXZaL88TOiUGY5ReO+Gp8Cf9IibK1WUuE+FiKz9/xnu4YCl50WJcd0AvjQN126hHLMmuPPEF2dBtSSztfBDrAzJc8pg6NeEzRLK/WTFEzvVM0mR+R/tUUbR1nq94cFvOO25+sH05/wXlpR5gRRbv2BBwaJ1fyIOePQdEIyviyWwd7uS25csC2ouUOJ67O50BjOGmN6shA0BXtnti9HDp6JLcfIKvK7Cgz5Cj/g0Umm2lgZ5uRNoozd76kgzFKuQgZYHuf9njdjAJnDxjI0LR10R1iYp8R8NBO9qCDSOJRu8+pPAhZK3XG4dpbIcAa9djuagDni54wgppA7pTWJMsHZbwlr9Phw7J/BsRn1hW/DHzwMiUn3hXCOLDwAUVLkPKgMip5tYAh+00j7c9yZmpqRxsNd+ve+6LA/XUebJ24ZIcUaaq2pdQTLcCNRTdby9d+Wj0p/AHIWCdI+dH+/r7qYpUWDQSkUwJ5AAVQpvEJGpf6rLwvZ0GPjIXM8bLbY2kIjBORHhTvdbughQIlnWN7dmnJSlAFdxo66EadB6leLNftIkChThTft3pleJw7D2zFodFB7YBUoSK9QhF5NR64qHMJgcsp1qS1YdUWHDQyZpPV8DVhbyJG9/nnL3zjJbQlSMC+N0DOigHJ2XhcaNz1TyKqYWxYnaW7JpLpiTIO9mnhwjk1VRyTbtwm+YYdGBT9NN79rLVFQeoPSuMC0dmDfXHVRmWKKR9+78cDu3iwDz6bXrw6zaBiMEQgeMyJl6NPhlL4LSZntKurI/4jo3KvAhKANyBU8TBZqipfB5FMG8L8t+9kYibEdgzWrxA+P4dYB1nu0C7RbmVZUMDypNKcdI4QLyJUa0ptlG66pSIiopBevbH8nEvw9JIESrhaDbu6PYR/bhDMI5SUpwPQtRIcmt3ldFmvicwgFGFBMfYhSClZUbyNZ7Ik/Nwp/43po3lRLt4sENB+Ms7+ClD7/IS567TXUOq5pFIUUs1aSP9/3T0UAb0vVjuHyT02y1WSzZKdQ7gO5WbzDIpNgieYxgcS9y5quCfgrhWQZIH3A5JkvU07wIeuOhTGKckxHLoyraWaHjH+Pg90JzXJWMCbVJV0jNkUNgPKGZCOlD/1R6C1LgRbai6Ah3HzLizvjxFtNf6pSnB5dd90DAPGuCcBq9hV7Vo7UIYi88CG81E1KPe57PoAyUbDZUJnDZlvJa3LS3bGw737RZIAVbEmxO7MBdMZ3jj4C3CMPDpNXVD024PEbfdxhUazrOIgUpg6ubYuAt8h1UiomfJMxjXW0lK+pas+tX0Ks8oWAo8eB6WZc4QIsepYPe6eMe2+teFDTUxtpE6z4T+7Xtk4KxDwSRV6F7ItBjezwaSSN9tWbH3qRCR+SH1hUDcGLh4cTVrcVW1S9w5p18Knt36arunMQqULSamHk1SI90zYDpITV5Xm0sPzWrkKCPjMuf7FlPwQCT8512hAVuXlDIjyC6OARoj9cRmLgHvF9II0DaefrkmvYnt+9HLNwcZBFLRw9oWd9ucS1AQTlADOa4CtMId2pmGMl9v+mJ+xnUstRVXHB1wcqycXyuBNS4ag6Gqt+cM2dfAN2WdHISKy3pfZK5oMZXHtuxwuDgyu/ZyUfiedUdB5VN/M+GySq0NwMdrYgy5XIFueDep8qF0PR7U3Q1fDqhT96+tyEpq5WzRh7upRURrkhVWD1DfWvMPHt4GrwEJ3Lwsd1ZHChtK/UUXM0YY3yLMdU0Qk5ITVd3dY9m6qOpo6Db6PwpoqofYYh3gNnqgJV4qrryGfjkmsyLMfRx2xEDzuRY20px1loYI5EUFmz5kzsFDvwd9cJMZLiffyLP9RVajM+ObEWrE/ZdB8ENpja6OLdaZPhu3JxcjMnoOHj64Iew3PoV4X6gtLwYLLikyK80BRgfR2ILlhfOR2/7ejAkDu6jCYeevKCeJ+doAtbR3vBDsuS6ZXUXfBlcTPRETPz17EOq2kLGRNi322KLxOy1Okj8EVOZBvPa1Qwprtyvz+FCgqTDWX3T6oK/Iee/FX5lzXtiyi1CPmhwv3BHbznCTzZWq7ej0dHmYnmFzcEhQAYnt9YEw5eZF68qCrCpwxDqnoQ093UkAvbq4oqaBXl/EO+BiTDP/OtAULTrOmVkUt2DtktukeiQh4Eu1uREPzaRShj+gjBhzA+XPdLJd/ud4pqJWPEbuv8Nndsz0j/x+ph1U56DbSGs2i169yFjZR4MqMM4KYmh9QjK4Fryub7WmjsD2huCeyPCTewE86hzadxFp/xdkFUj7ba4tuJJEHfz3X3afW3x/Dk+2+nLUs4com8EAEanJvSRQ8ROhyxIRmK+FjSbbgdsyHLwXzt2ELMwXAqN+U38xFwu2Z72sTv9s+RydmDSXpPE4orTbLXC58OU5/NfOUAVq2n+xZNAG/vYOMNbvwlSuLrf3OWzDEeWI7x6y8Y3aEIzNmdHJzReon6n6hfU3Mxh5oO1B7ueuTSEIfkF6Stiteu6bWE6xfNQYgBs4eeyBX4fQtLPREW2sryPXjDBy3/1+ztMqZnBDuiKmt+ISbFQTCXmJcgmjqqb4xnPW9rsqX7VUYROEX2tK3q9wdRNOnyh2otgoiSmrLxC39Zsbf+37sIQUh5meF9CchblD3G4yAEBoeGxLSJ68V8RroCKcgm4M+JshMH5bfzHPE5QcfOIjVnwRUWe7ClN/DBzScNSylzRGj8Ub5gWr3M3MQHqOQq8V77B+ZxeN8g392+cY+2vWKjhkcRvbB+ZqALrjdTR7O1SnYLIPIDw8Ng4qNCQUSe0fZ7q+QdFbE3EV/jpv1ntE9nhjKKPYDOIagAKP/YlMe0q8qc4TepSatkry7ZbWKZmqk+mggkMZXwXdAeBR35pjYynM4xxN7jW9rH4uXl9qHiMO8L7C5lWPQMw07S7lEiPfJIAAeXnEWD3z5U6wXsTCgRzCxqqtk6NbyJTCjT7YMjey/v1ogpXThb3MpaxqLiM2+t+TJ4jaItbcJqNm7t613aydHA86LKoBShl3wNalcw8z5VsP3EaQAQCmyEhEc1okJiYvI0r1WJgK0/K/5UAzTKe3vkKRnY9iPJH9v0i5obhyN2I+0MgRJ01rb66le9jCP7g6vNhT+gG1XO/IWvQ4uRV0OBPHC51WnO+TbfiQbDQ5qlwZsURGvlT2PoX5g1PTrnSml5KPjyWNY8r8g8GkKJ5b00hIMgc0H4vhRXE18GobdU5oYS26ss6YpATctvUvWAiDw8h5bqMyPFinjGoS4ScyJx0M3gG976TZvcX3bmBG11377wIqyyFqbGEPxTwTOM74TlQYeN+xX3PBcgPmM/h2koASZfDuLC9qaRhhaSrN2u3Qc7lE2/4/sFqtPbw1STq9QduqaErlOJ/KB3vtNqJeDHmPBsrv6c5Kg1kopHEjn8nlyMXjU6/CaRz7fraYBR5YNbF51x1VuWBmz5SIx5X8bOj/daskQYHazknvUTna1iy1d7xm4bMk7omOsqslsmkehwAKswgClrWsMLXXGQCo2nhWi+VDlhk+bYx19DGuS9S12nh19w+ZWuEaXgJQIJxR8+qRDiOBNZOA3lnPDkXG430dl1fhWdcRreNo1dYC2yAUosWhuQFehZ2oyF45r0Uljue4b6NyAU4BK9FTw4e7hPzwlnDqnAS/ZdB9qh/s2JWK49bXGZFXMK3l9eK5TPg2je+O4JbMTySW1itIiy+IDS+GhjiRZx22ertbIxAOUyWi05JplqlbgOw/cAJpJadNrPAatYJT1YCRTetG4NeKhAlo2muDgziplniQMw0g42JgzGdiqPWEkOJgcWmoqALh4hwpHI1fV9hXC04rEWp3eY2OvgCG/HXbBGAIlc+gFBGdmJH+XqNuQPLliRzY/YH9AWTXzd1H7/NwG38NtgofUQhBMPlVbfbfyzUrgMBe8Qk3mGEg42UCUX1nieLIALFUgd4H2uILIj56Rtoa5Ct4fF4Y3IRXdy8AAKbUzJplv09WJN8QfvuERp6ZTo1hHLbaietRdamyqsvnGuiMX8FbaO9EBaS+xjzJOTNpD8EoEyPiTWPkVKpkdIYplOetnPSLWx/R13fCHLM1hejYReaSVlK9sCW352MItn91eJjeN2Ej9Gs5CoVUBEeDqzIqEC4Yr5b/SFUA2RCpLK0dDwAUr2LPWWYva6XwoUPUnmrkoHMvQGqSVf69kIra44KZlA6bpKH/+35titi8L2rkeirY1+Ap4E3gJJOFPhtFdreGj0l0GHx5X8TqHLQKhCG3YcT6iTIq7RMPZJ7DJ2n2Sug1cfy9lb4jR+xCX3n6xtXdWUxQwDfGz2ZDpwgpDEqE7N4H05AAAAAAAAAACvnrUHCAGjo1vWK5u4UpDfiZtu64+MR+44QDRtn6K3L92wMHIDxsQgX0hM0fx7Ww/Zu21D85Cji67ILss4ddjckRbolOgeMzemTOWpZCrRUDTAZTTHiKgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA"
alt="Sea Blaster Logo">

  <!-- Secondary badge logo -->

<img class="secondary-logo"
src="data:image/png;base64,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"
alt="The Original Sea Blaster – Destin, Florida">

  <p class="hero-tagline">Destin, Florida &nbsp;·&nbsp; Social Media Partnership Proposal</p>

  <div class="price-badge">
    <span class="label">Monthly Investment</span>
    <span class="amount">$1,500</span>
    <span class="sub">per month · all platforms included</span>
  </div>

  <!-- Animated dolphins -->

  <div class="dolphin-scene">
    <!-- Dolphin 1 -->
    <div class="dolphin dolphin-1">
      <svg width="90" height="50" viewBox="0 0 90 50" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M5 30 Q20 10 45 18 Q65 24 80 15 Q72 28 60 30 Q75 35 85 28 Q78 42 60 38 Q40 45 20 38 Q10 42 5 38 Q8 33 5 30Z" fill="rgba(255,255,255,0.75)"/>
        <path d="M5 30 Q8 22 15 20 Q10 28 5 30Z" fill="rgba(255,255,255,0.5)"/>
        <ellipse cx="22" cy="22" rx="2" ry="2" fill="#0B3D6B"/>
        <path d="M60 30 Q70 20 80 15 Q72 28 60 30Z" fill="rgba(255,255,255,0.55)"/>
      </svg>
    </div>
    <!-- Dolphin 2 -->
    <div class="dolphin dolphin-2">
      <svg width="70" height="40" viewBox="0 0 70 40" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M4 23 Q15 8 35 14 Q50 19 62 11 Q56 22 46 24 Q58 28 66 22 Q60 33 46 30 Q30 36 15 30 Q8 33 4 30 Q6 26 4 23Z" fill="rgba(255,255,255,0.7)"/>
        <ellipse cx="17" cy="17" rx="1.8" ry="1.8" fill="#0B3D6B"/>
        <path d="M46 24 Q54 16 62 11 Q56 22 46 24Z" fill="rgba(255,255,255,0.5)"/>
      </svg>
    </div>
    <!-- Dolphin 3 (leaping) -->
    <div class="dolphin dolphin-3">
      <svg width="80" height="60" viewBox="0 0 80 60" fill="none" xmlns="http://www.w3.org/2000/svg">
        <g transform="rotate(-25,40,30)">
          <path d="M5 30 Q20 10 42 17 Q60 22 72 14 Q65 27 54 29 Q68 34 76 26 Q70 40 54 37 Q36 44 18 37 Q10 41 5 37 Q7 33 5 30Z" fill="rgba(255,255,255,0.8)"/>
          <ellipse cx="20" cy="21" rx="2" ry="2" fill="#082035"/>
          <path d="M54 29 Q65 20 72 14 Q65 27 54 29Z" fill="rgba(255,255,255,0.55)"/>
        </g>
        <!-- splash droplets -->
        <circle cx="10" cy="52" r="2" fill="rgba(255,255,255,0.4)"/>
        <circle cx="18" cy="56" r="1.2" fill="rgba(255,255,255,0.3)"/>
        <circle cx="6" cy="57" r="1.5" fill="rgba(255,255,255,0.25)"/>
      </svg>
    </div>
  </div>

  <!-- Wave bottom -->

  <div class="wave-bottom">
    <svg viewBox="0 0 1440 80" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M0,40 C240,80 480,0 720,40 C960,80 1200,10 1440,40 L1440,80 L0,80 Z" fill="#060E18"/>
    </svg>
  </div>
</section>

<!-- ═══════ PLATFORMS ═══════ -->

<section class="content">
  <div class="section-intro">
    <h2>Three Platforms.<br><span>One Unified Presence.</span></h2>
    <p>Tailored strategies for each platform—because what works on TikTok is a different art form than what converts on Facebook.</p>
  </div>

  <div class="platforms">
    <div class="platform-pill ig"><span class="dot"></span>Instagram</div>
    <div class="platform-pill tik"><span class="dot"></span>TikTok</div>
    <div class="platform-pill fb"><span class="dot"></span>Facebook</div>
  </div>

  <!-- Service cards -->

  <div class="cards">
    <div class="card">
      <span class="card-icon">📅</span>
      <h3>3× Weekly Posting</h3>
      <p>Consistent, scheduled content across all platforms to keep Sea Blaster top-of-mind every week of the season.</p>
    </div>
    <div class="card">
      <span class="card-icon">🎬</span>
      <h3>Content Creation Day</h3>
      <p>A dedicated shoot day each month capturing high-quality video and photos of the boat, crew, and Crab Island experience.</p>
    </div>
    <div class="card">
      <span class="card-icon">🗺️</span>
      <h3>Dual Strategy</h3>
      <p>Facebook &amp; Instagram strategy kept intentionally separate from TikTok—each platform gets a custom creative approach.</p>
    </div>
    <div class="card">
      <span class="card-icon">💬</span>
      <h3>Mild Engagement</h3>
      <p>Monitoring comments and DMs to keep the community warm and responsive without aggressive growth tactics.</p>
    </div>
    <div class="card">
      <span class="card-icon">🌊</span>
      <h3>Crab Island Presence</h3>
      <p>Prime real estate on Crab Island and Crab Island Girl channels—putting Sea Blaster where the audience already lives.</p>
    </div>
    <div class="card">
      <span class="card-icon">🤝</span>
      <h3>Curated Collabs</h3>
      <p>Strategic partnerships with select Destin businesses and local influencers to amplify reach authentically.</p>
    </div>
    <div class="card">
      <span class="card-icon">☀️</span>
      <h3>Specials Promotion</h3>
      <p>Personalised marketing strategies built around your seasonal deals, events, and last-minute availability pushes.</p>
    </div>
    <div class="card">
      <span class="card-icon">☁️</span>
      <h3>Cloud Asset Delivery</h3>
      <p>All footage and photos uploaded to a shared Dropbox or Google Drive—your content library, always accessible.</p>
    </div>
    <div class="card">
      <span class="card-icon">📊</span>
      <h3>Monthly Planning</h3>
      <p>A forward-looking content strategy session each month so we're always aligned on messaging, timing, and goals.</p>
    </div>
  </div>
</section>

<!-- ═══════ DELIVERABLES ═══════ -->

<section class="content">
  <div class="deliverables">
    <h2>What You <span>Get</span></h2>

```
<div class="deliver-item">
  <span class="deliver-num">01</span>
  <div class="deliver-text">
    <strong>Full platform management — Instagram, TikTok &amp; Facebook</strong>
    <p>End-to-end account ownership: captions, hashtags, scheduling, and platform-native optimisation.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">02</span>
  <div class="deliver-text">
    <strong>Monthly content creation day on location</strong>
    <p>Professional video and photo shoot capturing Sea Blaster's energy on and off the water.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">03</span>
  <div class="deliver-text">
    <strong>3 posts per week across all channels</strong>
    <p>12+ pieces of original content every month, formatted for each platform's best-performing format.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">04</span>
  <div class="deliver-text">
    <strong>Specials &amp; promotions marketing</strong>
    <p>Custom creative for deals, giveaways, and seasonal campaigns designed to drive bookings.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">05</span>
  <div class="deliver-text">
    <strong>Crab Island &amp; Crab Island Girl placement</strong>
    <p>Leveraging high-traffic Destin tourism channels where your audience is already looking.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">06</span>
  <div class="deliver-text">
    <strong>Collaborative brand partnerships</strong>
    <p>Hand-picked local collaborations that feel genuine—not forced—and expand reach organically.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">07</span>
  <div class="deliver-text">
    <strong>Shared cloud media library</strong>
    <p>Every photo and video delivered to your Dropbox or Drive folder — fully owned by you.</p>
  </div>
</div>
<div class="deliver-item">
  <span class="deliver-num">08</span>
  <div class="deliver-text">
    <strong>Monthly content strategy planning session</strong>
    <p>A collaborative review of the coming month's direction, themes, and posting calendar.</p>
  </div>
</div>
```

  </div>
</section>

<!-- ═══════ CTA ═══════ -->

<section class="cta">
  <h2>Let's Make <span>Waves</span><br>Together.</h2>
  <p>Sea Blaster · Destin, Florida</p>

  <!-- mini dolphin trio -->

  <div class="cta-dolphins">
    <svg width="60" height="35" viewBox="0 0 60 35" fill="none">
      <path d="M3 22 Q13 7 30 12 Q44 16 54 10 Q48 20 38 22 Q50 26 57 19 Q52 30 38 27 Q24 33 12 27 Q6 30 3 27 Q5 24 3 22Z" fill="rgba(255,255,255,0.65)"/>
      <ellipse cx="14" cy="15" rx="1.5" ry="1.5" fill="#0B3D6B"/>
    </svg>
    <svg width="50" height="30" viewBox="0 0 50 30" fill="none">
      <g transform="rotate(-15,25,15)">
        <path d="M2 18 Q10 5 25 9 Q36 13 44 8 Q39 17 31 18 Q41 22 47 16 Q42 25 31 23 Q19 27 9 23 Q4 25 2 23 Q3 20 2 18Z" fill="rgba(255,255,255,0.65)"/>
        <ellipse cx="11" cy="12" rx="1.3" ry="1.3" fill="#0B3D6B"/>
      </g>
    </svg>
    <svg width="65" height="38" viewBox="0 0 65 38" fill="none">
      <path d="M3 25 Q16 8 34 14 Q50 19 58 12 Q52 24 42 26 Q56 30 62 23 Q57 36 42 33 Q27 40 13 33 Q7 36 3 33 Q5 28 3 25Z" fill="rgba(255,255,255,0.65)"/>
      <ellipse cx="16" cy="18" rx="1.7" ry="1.7" fill="#0B3D6B"/>
    </svg>
  </div>
  <p style="color:rgba(255,255,255,0.25);font-size:0.78rem;letter-spacing:0.15em;text-transform:uppercase;margin-top:8px;">$1,500 / month · Content Creation Included</p>
</section>

</body>
</html>