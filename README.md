# Isaiah-Landing-Page
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vertical Jump Training System</title>
    <style>
        /* CSS Reset/Normalization */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html, body {
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Basic Styles */
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
            line-height: 1.6;
            background-color: #f4f4f9;
            color: #333;
        }

        .container {
            width: 100%;
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Typography */
        h1, h2, h3 {
            line-height: 1.2;
            margin-bottom: 1rem;
            color: #1a1a1a;
        }

        h1 {
            font-size: 2.5rem;
        }

        h2 {
            font-size: 2rem;
            margin-top: 3rem;
            padding-bottom: 0.5rem;
            border-bottom: 3px solid #0056b3;
        }

        p {
            margin-bottom: 1rem;
            font-size: 1.1rem;
            max-width: 700px;
        }

        b, strong {
            font-weight: 700;
        }

        /* Hero Section */
        .hero {
            background-color: #111;
            color: #fff;
            padding: 4rem 0;
            text-align: center;
        }

        .hero .preheader {
            font-size: 1rem;
            font-weight: 600;
            color: #bbdefb;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 1rem;
        }

        .hero h1 {
            font-size: 3rem;
            color: #fff;
        }

        .hero .subheader {
            font-size: 1.25rem;
            color: #e0e0e0;
            margin-top: 1rem;
            margin-bottom: 2rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* VSL Icon */
        .vsl-container {
            width: 100%;
            max-width: 640px;
            margin: 1.5rem auto 2.5rem;
            cursor: pointer;
            position: relative;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            border-radius: 8px;
            overflow: hidden;
        }

        .vsl-container img {
            display: block;
            width: 100%;
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }

        .play-button {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 80px;
            height: 80px;
            background-color: rgba(255, 0, 0, 0.85);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.2s ease-in-out, background-color 0.2s;
        }
        
        .vsl-container:hover .play-button {
            transform: translate(-50%, -50%) scale(1.1);
            background-color: rgba(255, 0, 0, 1);
        }

        .play-button::after {
            content: '';
            display: block;
            width: 0;
            height: 0;
            border-style: solid;
            border-width: 15px 0 15px 25px;
            border-color: transparent transparent transparent #fff;
            margin-left: 5px;
        }

        /* CTA Button */
        .cta-button {
            display: inline-block;
            background-color: #ffc107;
            color: #111;
            padding: 1rem 2.5rem;
            font-size: 1.25rem;
            font-weight: 700;
            text-decoration: none;
            border-radius: 5px;
            box-shadow: 0 4px 15px rgba(255, 193, 7, 0.4);
            transition: transform 0.2s, box-shadow 0.2s;
            border: none;
            cursor: pointer;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 7px 20px rgba(255, 193, 7, 0.5);
        }

        /* Content Sections */
        .content-section {
            padding: 4rem 0;
            border-bottom: 1px solid #ddd;
        }

        .content-section:last-child {
            border-bottom: none;
        }

        /* Bullets */
        .outcome-bullets {
            list-style: none;
            margin-top: 2rem;
        }
        .outcome-bullets li {
            font-size: 1.1rem;
            padding: 1rem;
            margin-bottom: 1rem;
            background: #e3f2fd;
            border-left: 5px solid #007bff;
            display: flex;
            align-items: center;
        }
        .outcome-bullets li::before {
            content: '✓';
            font-size: 1.5rem;
            color: #007bff;
            margin-right: 1rem;
            font-weight: bold;
        }

        /* Testimonial */
        .testimonial {
            background-color: #fff;
            border: 1px solid #ddd;
            padding: 1.5rem;
            margin: 2rem 0;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }
        .testimonial p {
            margin-bottom: 0.5rem;
            font-style: italic;
        }
        .testimonial cite {
            display: block;
            text-align: right;
            font-weight: bold;
            color: #555;
        }
        
        /* Offer Section */
        .offer {
            background: #fff;
            padding: 2.5rem;
            margin-top: 2rem;
            text-align: center;
            border-radius: 8px;
            border: 2px dashed #ffc107;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .price-strikethrough {
            text-decoration: line-through;
            color: #999;
            font-size: 1.5rem;
        }
        .price-main {
            font-size: 3.5rem;
            font-weight: 700;
            color: #0056b3;
            margin: 0.5rem 0;
        }
        .price-clarifier {
            font-weight: bold;
            margin-bottom: 1.5rem;
        }
        .guarantee {
            margin-top: 2rem;
            font-weight: bold;
        }
        .guarantee-box {
            border: 2px solid #28a745;
            padding: 1rem;
            margin-top: 1rem;
            border-radius: 5px;
            background-color: #e8f5e9;
        }
        .guarantee-box p {
            margin: 0;
        }

        /* FAQ Section */
        .faq-item {
            margin-bottom: 1.5rem;
        }
        .faq-item h3 {
            font-size: 1.2rem;
            color: #0056b3;
            margin-bottom: 0.5rem;
        }

        /* Responsive Media Queries */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            .hero h1 {
                font-size: 2.5rem;
            }
            .play-button {
                width: 60px;
                height: 60px;
            }
            .play-button::after {
                border-width: 12px 0 12px 20px;
            }
            .content-section {
                padding: 3rem 0;
            }
            p {
                font-size: 1rem;
            }
            .cta-button {
                padding: 0.8rem 2rem;
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>

    <header class="hero">
        <div class="container">
            <p class="preheader">FOR ATHLETES WHO ARE DONE WITH PLATEAUS</p>
            <h1>Add 3-12 Inches To Your Vertical In As Little As One Month Using Our "Coached-Science" Method</h1>
            <p class="subheader">And finally do it without the soul-crushing knee pain from generic, cookie-cutter jump programs.</p>

            <div class="vsl-container">
                <img src="https://via.placeholder.com/640x360.png/000000/FFFFFF?text=Click+To+See+How" alt="Video presentation about the jump program">
                <div class="play-button"></div>
            </div>

            <a href="#offer" class="cta-button">CLAIM YOUR SPOT (FOR 90% OFF)</a>
        </div>
    </header>

    <main>
        <section class="content-section">
            <div class="container">
                <h2>That Split-Second Of Hangtime… Or The Agonizing Thud Of A Missed Dunk.</h2>
                <p>You know the feeling.</p>
                <p>You’ve seen the videos. You’ve pictured it in your head a thousand times. That moment you just… <em>float.</em></p>
                <p>But when you try, something is missing. There's a ceiling you just can't break through.</p>
                <p>You've tried everything, haven't you? Endless calf raises. Box jumps until your shins ache. You've probably even bought one of those "secret" jump programs that turned out to be a glorified PDF of exercises you already knew.</p>
                <p>You’ve wasted hours in the gym, money on useless routines, and what do you have to show for it?</p>
                <p>A vertical that’s stubbornly stuck. Nagging pain in your knees, your back, or your Achilles that screams at you after every session. And the quiet, gut-wrenching fear that you might have already hit your genetic limit.</p>
                <p>Every day you do nothing, your competition is getting faster, stronger, and higher.</p>
                <p>What if the problem isn’t your work ethic? What if the problem is the *method* itself? What if you’ve been building your engine with the wrong parts… and a simple, proven fix could change everything?</p>
                <div class="testimonial">
                    <p>“If you're contemplating getting the program... I’ve gained about 6 inches to my max vert since starting in March. If you're contemplating getting the program, I would say it is worth it!”</p>
                    <cite>- Reddit User, r/ProDunking</cite>
                </div>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <h2>How A World-Record Jumper Threw Out The Old Playbook To Build Injury-Proof Hops</h2>
                <p>I was just like you.</p>
                <p>Obsessed with jumping higher. I followed all the “gurus.” I did the high-impact, joint-destroying workouts that promised the world. And for a while, it worked… until it didn't.</p>
                <p>My vertical went up, but so did the pain. My knees felt like grinding gravel. My progress hit a wall, hard.</p>
                <p>The standard advice almost ended my career. It was all based on volume, not science. More reps, more jumps, more punishment. It ignored one fundamental truth: <strong>every athlete is different.</strong></p>
                <p>Frustrated and injured, I went back to square one. I dove into university-level biomechanics, kinesiology, and sports science with my coach. We threw out the “bro science” and focused on what the data actually said about force production, tendon health, and athletic ceilings.</p>
                <p>We realized conventional jump programs fail because they are one-size-fits-all. They don't account for your body, your history, your equipment, or your specific weaknesses.</p>
                <p>They can’t see that your takeoff angle is off by 3 degrees, or that your force leak is costing you 4 inches.</p>
                <p>So we built the opposite. A system that doesn’t just give you exercises… it gives you a coach. A system that doesn’t just hope you get it right… it analyzes your form and tells you exactly what to fix. A system that adapts to YOU.</p>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <h2>This Isn’t A “Program.” It’s A Personalized Coaching System.</h2>
                <p>Forget everything you think you know about online training. This is not another PDF download or a folder of pre-recorded videos.</p>
                <p>Our <strong>"Coached-Science" Method</strong> is a two-part system designed for one thing: getting you measurable results, safely.</p>
                <p><strong>Part 1: The University-Level Course.</strong> You’ll finally understand the *science* behind jumping. No more blindly following exercises. You'll learn the physics of the jump, how to manage fatigue, and how to become your own best coach for the rest of your life.</p>
                <p><strong>Part 2: The Daily Custom Coaching.</strong> This is where the real progress happens. Every single day, you get custom workouts sent to you. You film your main lifts and jumps, send them to us, and we send back detailed video analysis. We are your eyes, correcting your form and ensuring every single rep is making you better, not just tired.</p>
                <p>Imagine knowing, with 100% certainty, that your training is working.</p>
                <p>Imagine seeing your form get cleaner week by week, and your vertical test numbers climbing higher and higher.</p>
                <p>That’s the difference between guessing and knowing.</p>

                <ul class="outcome-bullets">
                    <li><strong>Custom Daily Workouts based on YOUR needs</strong> &rarr; so you stop wasting time on generic exercises and start fixing the exact weaknesses holding you back from a higher vertical. You become an efficient, intelligent athlete.</li>
                    <li><strong>Personalized Video Technique Analysis from expert coaches</strong> &rarr; giving you the confidence that your form is perfect and safe, turning you into the kind of athlete who moves with precision and power.</li>
                    <li><strong>Injury-Specific Rehab Protocols built into your training</strong> &rarr; so you can finally train without the fear of knee, back, or Achilles pain, and feel strong and resilient every time you step on the court or field.</li>
                    <li><strong>Access to a University-Level Jump Science Course</strong> &rarr; which means you're not just following a plan, you're mastering the principles of performance, making you a smarter and more autonomous athlete for life.</li>
                </ul>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <h2>Your Personal Performance Lab, Open 24/7.</h2>
                <p>When you join today, you're not buying a product. You're getting a key to a complete coaching environment.</p>
                <p>Here’s exactly what you get inside:</p>
                <ul>
                    <li><p><strong>Custom Daily Workouts:</strong> No more wondering what to do. We tell you exactly what exercises, sets, and reps to perform each day, tailored to your goals, equipment, and schedule.</p></li>
                    <li><p><strong>24/7 Group Chat With Coaches:</strong> Got a question at 10 PM? Need a last-minute adjustment? We're there. This ends the feeling of training alone.</p></li>
                    <li><p><strong>Jump & Lift Technique Video Analysis:</strong> This is the core of the system. It’s like having a world-class coach standing over your shoulder for every important lift, correcting the small mistakes that make a huge difference.</p></li>
                    <li><p><strong>The Complete Jump Science Course:</strong> Your permanent library for understanding elite athletic performance.</p></li>
                    <li><p><strong>Specific Rehab For Nagging Pains:</strong> We don't just work around injuries; we help you fix the root cause so you can come back stronger.</p></li>
                    <li><p><strong>Group Calls With Record Holders:</strong> Learn directly from athletes who have been where you are and reached the highest levels.</p></li>
                </ul>
                <p>This isn’t about just adding inches. It’s about building a body that performs on command, without breaking down.</p>
            </div>
        </section>

        <section id="offer" class="content-section">
            <div class="container">
                <h2>For A Limited Time, Get Coached For Less Than The Price Of A Pizza.</h2>
                <p>A personal coach who analyzes your videos and builds your daily plan can cost upwards of $500 per month. Even basic template programs sell for more than $100.</p>
                <p>Because we deliver this system with a small, dedicated team, we can keep the costs reasonable. The normal investment for this level of daily, hands-on coaching is $127 a month.</p>
                <p>But right now, because we are looking for a few more dedicated athletes to build into new success stories, we're doing something special.</p>

                <div class="offer">
                    <p>Get Your First Month Of Full Coaching For:</p>
                    <p class="price-strikethrough">$127</p>
                    <p class="price-main">$12.70</p>
                    <p class="price-clarifier">(That's 90% OFF - Only For A Limited Time)</p>
                    <a href="#" class="cta-button">CLAIM YOUR SPOT FOR JUST $12.70</a>
                    <div class="guarantee">
                        <p>And your small investment is protected by two iron-clad guarantees.</p>
                        <div class="guarantee-box">
                            <p><strong>Guarantee #1: The 30-Day Jump Guarantee.</strong> If you’re not injured, are out-of-season, and have less than two years of serious training, we guarantee you will jump higher in your first month. If you don't, just show us your logs. We'll refund every penny.</p>
                        </div>
                        <div class="guarantee-box">
                            <p><strong>Guarantee #2: The 7-Day Knee Pain Relief Guarantee.</strong> Follow our instructions for one week. If your knee pain hasn't noticeably dropped, ask for your money back. Simple as that.</p>
                        </div>
                    </div>
                </div>
                <p style="text-align: center; margin-top: 2rem;"><strong>Why the massive discount?</strong> Frankly, our best marketing is your results. We know that once you experience this level of coaching, you'll stay. But we have to limit this offer because we personally analyze every video submission. Once our current coaching slots are full, the price goes back to $127.</p>
            </div>
        </section>

        <section class="content-section">
            <div class="container">
                <h2>Your Questions, Answered.</h2>
                <div class="faq-item">
                    <h3>What if I don't have much time to train?</h3>
                    <p>That's exactly why you need this. A custom plan focuses on the 20% of exercises that deliver 80% of the results. A focused 45-minute session we design for you is better than 2 hours of guessing on your own. We build the plan to fit YOUR schedule.</p>
                </div>
                <div class="faq-item">
                    <h3>Can I do this if I'm currently in-season for my sport?</h3>
                    <p>Absolutely. This is one of our specialties. The worst thing you can do is follow a high-volume "beast mode" program during your season. We adjust your training load to keep you fresh and explosive for game day, while still making progress.</p>
                </div>
                <div class="faq-item">
                    <h3>Does this work for [basketball, volleyball, track, etc.]?</h3>
                    <p>Yes. The principles of generating vertical force are universal. The ability to jump higher and land safer is critical for nearly every sport. We've coached basketball players, track athletes, ultimate frisbee competitors, football players, and even bobsledders.</p>
                </div>
                <div class="faq-item">
                    <h3>What if I don't have access to a gym or any equipment?</h3>
                    <p>No problem. Your daily workouts are built around the equipment you have. Whether that's a state-of-the-art weight room, a few resistance bands, or just your own bodyweight in your garage, we create the perfect plan for you.</p>
                </div>
                <div class="faq-item">
                    <h3>Why is the first month so inexpensive? Is there a catch?</h3>
                    <p>No catch. We're confident that once you experience what real coaching feels like—seeing your numbers go up and your pain go down—you'll see the immense value. We're offering this low entry price to prove it to you. We can only do this for a limited number of new athletes before our coaching capacity is full and the price returns to normal.</p>
                </div>
                <p style="text-align: center; margin-top: 3rem; font-size: 1.2rem;">Don't spend another month stuck at the same height.</p>
                <p style="text-align: center;">It's time to feel what it's like to train smarter, feel better, and finally see the results your hard work deserves.</p>
                <div style="text-align: center; margin-top: 2rem;">
                     <a href="#offer" class="cta-button">CLAIM MY 90% OFF SPOT NOW</a>
                </div>
            </div>
        </section>
    </main>

</body>
</html>
