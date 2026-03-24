# techboy15.github.io
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title>Rod The Pug - Your Friendly Furry Companion</title>
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <style>
        :root{--bg:#ffffff;--card:#ffffff;--accent:#ffa20c;--muted:#bdd8ff;--text:#e6eef8}
        html,body{height:100%;margin:0;font-family:Inter,Segoe UI,Roboto,Helvetica,Arial,sans-serif;background:linear-gradient(180deg,#071028 0%, #081827 100%);color:var(--text)}
        .app{max-width:760px;margin:36px auto;padding:20px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);border-radius:12px;box-shadow:0 6px 30px rgba(2,6,23,0.6)}
        header{display:flex;align-items:center;gap:12px;margin-bottom:12px}
        .avatar{width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,#ffffff,#ff0000);display:flex;align-items:center;justify-content:center;font-size:28px}
        h1{font-size:18px;margin:0}
        .subtitle{font-size:12px;color:var(--muted);margin-top:4px}
        .chat{height:440px;overflow:auto;padding:16px;border-radius:10px;background:linear-gradient(180deg,rgba(255,255,255,0.01),transparent);border:1px solid rgba(255,255,255,0.03)}
        .msg{display:flex;gap:10px;margin-bottom:12px;align-items:flex-start}
        .msg.me{flex-direction:row-reverse}
        .bubble{max-width:78%;padding:10px 12px;border-radius:12px;background:rgba(255,255,255,0.03);font-size:14px;color:var(--text);line-height:1.3}
        .msg.me .bubble{background:linear-gradient(90deg,rgba(250,186,77,0.12),rgba(250,186,77,0.06));border:1px solid rgba(0, 0, 42, 0.12);color:var(--text)}
        .meta{font-size:11px;color:var(--muted);margin-top:6px}
        .composer{display:flex;gap:10px;margin-top:12px}
        input[type="text"]{flex:1;padding:10px 12px;border-radius:10px;border:1px solid rgba(255,255,255,0.03);background:transparent;color:var(--text);outline:none}
        button{background:var(--accent);border:none;color:#071022;padding:10px 14px;border-radius:10px;cursor:pointer;font-weight:600}
        .typing{width:48px;height:24px;border-radius:8px;background:rgba(255,255,255,0.02);display:flex;align-items:center;justify-content:center;color:var(--muted);font-size:12px}
        footer{font-size:12px;color:var(--muted);margin-top:10px;text-align:center}
        @media (max-width:520px){.app{margin:12px}}
    </style>
</head>
<body>
    <main class="app" role="main">
        <header>
            <div class="avatar" aria-hidden>🐶</div>
            <div>
                <h1>Rod AI</h1>
                <div class="subtitle">Your friendly furry companion</div>
            </div>
        </header>

        <section class="chat" id="chat" aria-live="polite"></section>

        <div class="composer">
            <input id="input" type="text" placeholder="Ask me something..." autocomplete="off" />
            <button id="send">Send</button>
        </div>

        <footer>Press Enter to send. This chat is AI free, just a simple chatbot, so don't expect anything too intelligent! (More knowledge will be programmed into Rod over time! Keep checking back, your furry companion might be smarter that last time you checked!)</footer>
    </main>

    <script>
        // puter.js (inline): simple client-side AI-like responder for "Rod The Pug"
        class Puter {
            constructor(name = 'Rod The Pug') {
                this.name = name;
                this.personality = [
                    "ruff, ruff!",
                    "woof!",
                    "ruff!",
                    "woof, woof!"
                ];
            }

            // Very small rule-based responder to mimic "AI" persona
            async getReply(text) {
                text = (text || "").trim();
                if (!text) return "You didn't say anything — Rod tilts his head. 🐶";

                const low = text.toLowerCase();

                // greetings
                if (/(hi|hello|hey|yo|greetings|what's up|Howdy)\b/.test(low)) {
                    return this._choose([
                        `Hey! Rod The Pug here — ${this._randPersona()}. How can I help?`,
                        `Woof! Hey! ${this._randPersona()}.`
                    ]);
                }

                // feelings
                if (/(how are you|how's it going|how are you doing)\b/.test(low)) {
                    return this._choose([
                        "I'm a happy pug — tail's wagging! How about you?",
                        "Feeling good and sniffing the breeze. 🐾",
                        "All's pawsome here! Just enjoying the day. What about you?",
                        "I'm really happy to chat with you! How are you doing?"
                    ]);
                }

                // ask name

                // jokes
                if (/(joke|funny|make me laugh|tell me a joke)\b/.test(low)) {
                    return this._choose([
                        "Why did the pug sit in the shade? Because he didn't want to be a hot dog. 😆",
                        "I tried to fetch the internet, but I brought back a stick. Works fine.",
                        "What do you call a dog magician? A labracadabrador! 🪄🐶",
                        "Why don't dogs make good dancers? Because they have two left feet! 🐾",
                        "What do you call a dog that designs buildings? A bark-itect! 🏢🐕",
                        "What do you call a dog that can sing? A melody shepherd! 🎤🐕",
                        "Why did the pug go to school? Becuase he was the teacher's pet! 🎓🐶"

                    ]);
                }

                // dog facts
                if (/(dog fact|dog facts|tell me something about dogs|do you know any dog facts|what are some dog facts)\b/.test(low)) {
                    return this._choose([
                        "Pugs are a brachycephalic breed — that means they have short noses and lots of character!",
                        "Dogs can learn many human words; some dogs know 200+ words.",
                        "Pugs were bred to be companions for Chinese royalty — they've been beloved lap dogs for centuries!",
                        "Dogs have a sense of time — they can miss you when you're gone and know when it's time for their walk! 🐾",
                        "Pugs have a unique snorting sound that's part of their charm — it's like they're always trying to talk!",
                        "Dogs have three eyelids! The third one helps keep their eyes moist and protected.",
                        "Pugs are known for their charming wrinkles — each pug's wrinkles are unique, like a fingerprint!",
                        "Dogs can smell about 100,000 times better than humans — no wonder they love sniffing everything!"
                    ]);
                }

                // help / capabilities

                // farewell
                if (/(bye|goodbye|see you|later)\b/.test(low)) {
                    return this._choose([
                        "Bye! Woof! 🐶",
                        "See ya! Nap time for Rod."
                    ]);
                }
                 if (/(i hate you|you're a jerk|you suck|you are a jerk|you are awful|you're dumb)\b/.test(low)) {
                    return this._choose([
                        "That's not very nice!",
                        "Woof! That's a bit harsh, but I'll still be here if you want to chat."
                    ]);
                }
                 if (/(i am sick|i have a cold|i'm sick|i'm sick and in the hospital)\b/.test(low)) {
                    return this._choose([
                        "Oh no, I'm sorry to hear that! I hope you feel better soon. Remember to rest and drink plenty of fluids!",
                        "Get well soon! 🐾"
                    ]);
                }
                 if (/(what does pi approximately equal|what's the value of pi|what is the value of pi)\b/.test(low)) {
                    return this._choose([
                        "The value of pi is approximately 3.14159. It's an irrational number that represents the ratio of a circle's circumference to its diameter! π",
                    ]);
                }
                 if (/(what is macbook neo|mac neo|macbook neo|new cheap mac|new cheap macbook)\b/.test(low)) {
                    return this._choose([
                        "The MacBook Neo is a sleek and powerful laptop that's perfect for both work and play!",
                        "The new MacBook Neo is here! It's got all the latest features and a stunning design."
                    ]);
                }
             if (/(new mac price|what is the price of the macbook neo|neo price|macbook neo price)\b/.test(low)) {
                    return this._choose([
                        "The MacBook Neo is priced starting at $599, making it an affordable option for those looking for a powerful and stylish laptop!",
                        "The price of the MacBook Neo starts at $599, offering great value for its features and performance!",
                        "The MacBook Neo is the Apple's most affordable laptop, starting at just $599! It's a great choice for students and anyone on a budget looking for a high-quality device."
                    ]);
                }
                    if (/(help with homework|i have homework i want help with|can you help me with some homework|homework help|could you help me with some homework?|I need help with my homework|I have homework that I need help with)\b/.test(low)) {
                        return this._choose([
                            "Sure! I'd be happy to help with your homework. I can only do basic math operations. What operation do you need assistance with?"
                        ]);
                    }
                     if (/(division|divide|division homework)\b/.test(low)) {
                        return this._choose([
                            "I can help with division! Just give me the numbers you want to divide, and I'll show you how to do it.",
                            "Division can be tricky, but I'm here to help! What numbers are you trying to divide?"
                        ]);
                    }
                  if (/(addition|add|addition homework|sum)\b/.test(low)) {
                        return this._choose([
                            "I can help with addition! Just give me the numbers you want to add, and I'll show you how to do it.",
                            "Addition can be tricky, but I'm here to help! What numbers are you trying to add?"
                        ]);
                    }
                    if (/(subtraction|subtract|subtraction homework|difference)\b/.test(low)) {
                        return this._choose([
                            "I can help with subtraction! Just give me the numbers you want to subtract, and I'll show you how to do it.",
                            "Subtraction can be tricky, but I'm here to help! What numbers are you trying to subtract?"
                        ]);
                    }
                    if (/(multiplication|multiply|multiplication homework|product)\b/.test(low)) {
                        return this._choose([
                            "I can help with multiplication! Just give me the numbers you want to multiply, and I'll show you how to do it.",
                            "Multiplication can be tricky, but I'm here to help! What numbers are you trying to multiply?"
                        ]);
                    }
                    if (/(30 minus 15|30 - 15|30 take away 15|30 - 15 difference)\b/.test(low)) {
                        return this._choose([
                            "30 minus 15 equals 15. You can think of it as starting with 30 and taking away 15, which leaves you with 15.",
                            "The answer to 30 minus 15 is 15. It's like having 30 cookies and giving away 15, so you have 15 cookies left!"
                        ]);
                    }
                    if (/(14 plus 15|14 + 15|14 and 15|14 + 15 sum)\b/.test(low)) {
                        return this._choose([
                            "14 plus 15 equals 29. You can think of it as starting with 14 and adding 15, which gives you 29.",
                            "The answer to 14 plus 15 is 29. It's like having 14 cookies and getting 15 more, so you have 29 cookies!"
                        ]);
                    }
                     if (/(4 times 5|4 * 5|4 and 5|4 * 5 product|4 x 5|4 multiplied by 5|4 x 5 product)\b/.test(low)) {
                        return this._choose([
                            "4 times 5 equals 20. You can think of it as having 4 groups of 5, which gives you 20.",
                            "The answer to 4 times 5 is 20. It's like having 4 baskets with 5 apples in each basket, so you have 20 apples!"
                        ]);
                    }
                    if (/(what is 12 divided by 4|divide 12 by 4|12 divided by 4)\b/.test(low)) {
                        return this._choose([
                            "12 divided by 4 equals 3. You can think of it as splitting 12 into 4 equal parts, and each part would be 3.",
                            "The answer to 12 divided by 4 is 3. It's like sharing 12 cookies between 4 friends, and each friend gets 3 cookies!"
                        ]);
                    }
                     if (/(what is 18 divided by 6|divide 18 by 6|18 divided by 6)\b/.test(low)) {
                        return this._choose([
                            "18 divided by 6 equals 3. You can think of it as splitting 18 into 6 equal parts, and each part would be 3.",
                            "The answer to 18 divided by 6 is 3. It's like sharing 18 cookies between 6 friends, and each friend gets 3 cookies!"
                        ]);
                    }
                     if (/(what is 9 divided by 3|divide 9 by 3|9 divided by 3)\b/.test(low)) {
                        return this._choose([
                            "9 divided by 3 equals 3. You can think of it as splitting 9 into 3 equal parts, and each part would be 3.",
                            "The answer to 9 divided by 3 is 3. It's like sharing 9 cookies between 3 friends, and each friend gets 3 cookies!"
                        ]);
                    }
                     if (/(what is 8 divided by 2|divide 8 by 2|8 divided by 2)\b/.test(low)) {
                        return this._choose([
                            "8 divided by 2 equals 4. You can think of it as splitting 8 into 2 equal parts, and each part would be 4.",
                            "The answer to 8 divided by 2 is 4. It's like sharing 8 cookies between 2 friends, and each friend gets 4 cookies!"
                        ]);
                    }
                     if (/(what is half of ten|half of ten|10 divided by two|divide ten by two|10 over two)\b/.test(low)) {
                        return this._choose([
                            "Half of ten is five. You can think of it as splitting ten into two equal parts, and each part would be five.",
                            "The answer to half of ten is five. It's like sharing ten cookies between two friends, and each friend gets five cookies!"
                        ]);
                    }
                     if (/(what is half of 20|half of 20|20 divided by two|divide 20 by two|20 over two)\b/.test(low)) {
                        return this._choose([
                            "Half of 20 is 10. You can think of it as splitting 20 into two equal parts, and each part would be 10.",
                            "The answer to half of 20 is 10. It's like sharing 20 cookies between two friends, and each friend gets 10 cookies!"
                        ]);
                    }
                     if (/(what is half of 100|half of 100|100 divided by two|divide 100 by two|100 over two)\b/.test(low)) {
                        return this._choose([
                            "Half of 100 is 50. You can think of it as splitting 100 into two equal parts, and each part would be 50.",
                            "The answer to half of 100 is 50. It's like sharing 100 cookies between two friends, and each friend gets 50 cookies!"
                        ]);
                    }
                    if (/(what is 16 divided by 4|divide 16 by 4|16 divided by 4)\b/.test(low)) {
                        return this._choose([
                            "16 divided by 4 equals 4. You can think of it as splitting 16 into 4 equal parts, and each part would be 4.",
                            "The answer to 16 divided by 4 is 4. It's like sharing 16 cookies between 4 friends, and each friend gets 4 cookies!"
                        ]);
                    }
                     if (/(what is 24 divided by 6|divide 24 by 6|24 divided by 6)\b/.test(low)) {
                        return this._choose([
                            "24 divided by 6 equals 4. You can think of it as splitting 24 into 6 equal parts, and each part would be 4.",
                            "The answer to 24 divided by 6 is 4. It's like sharing 24 cookies between 6 friends, and each friend gets 4 cookies!"
                        ]);
                    }
                     if (/(what is 6 divided by 2|divide 6 by 2|6 divided by 2)\b/.test(low)) {
                        return this._choose([
                            "6 divided by 2 equals 3. You can think of it as splitting 6 into 2 equal parts, and each part would be 3.",
                            "The answer to 6 divided by 2 is 3. It's like sharing 6 cookies between 2 friends, and each friend gets 3 cookies!"
                        ]);
                    }
                     if (/(what is 18 divided by 3|divide 18 by 3|18 divided by 3)\b/.test(low)) {
                        return this._choose([
                            "18 divided by 3 equals 6. You can think of it as splitting 18 into 3 equal parts, and each part would be 6.",
                            "The answer to 18 divided by 3 is 6. It's like sharing 18 cookies between 3 friends, and each friend gets 6 cookies!"
                        ]);
                    }
                     if (/(what is 25 divided by 5|divide 25 by 5|25 divided by 5)\b/.test(low)) {
                        return this._choose([
                            "25 divided by 5 equals 5. You can think of it as splitting 25 into 5 equal parts, and each part would be 5.",
                            "The answer to 25 divided by 5 is 5. It's like sharing 25 cookies between 5 friends, and each friend gets 5 cookies!"
                        ]);
                    }
                     if (/(what is 36 divided by 6|divide 36 by 6|36 divided by 6)\b/.test(low)) {
                        return this._choose([
                            "36 divided by 6 equals 6. You can think of it as splitting 36 into 6 equal parts, and each part would be 6.",
                            "The answer to 36 divided by 6 is 6. It's like sharing 36 cookies between 6 friends, and each friend gets 6 cookies!"
                        ]);
                    }
                     if (/(what is 49 divided by 7|divide 49 by 7|49 divided by 7)\b/.test(low)) {
                        return this._choose([
                            "49 divided by 7 equals 7. You can think of it as splitting 49 into 7 equal parts, and each part would be 7.",
                            "The answer to 49 divided by 7 is 7. It's like sharing 49 cookies between 7 friends, and each friend gets 7 cookies!"
                        ]);
                    } 
                    if (/(what is 64 divided by 8|divide 64 by 8|64 divided by 8)\b/.test(low)) {
                        return this._choose([
                            "64 divided by 8 equals 8. You can think of it as splitting 64 into 8 equal parts, and each part would be 8.",
                            "The answer to 64 divided by 8 is 8. It's like sharing 64 cookies between 8 friends, and each friend gets 8 cookies!"
                        ]);
                    }
                    if (/(let's play 20 questions|20 questions|can we play 20 questions)\b/.test(low)) {
                        return this._choose([
                            "Of course! I'll think of something, and you have to guess what it is by asking yes or no questions. Ready? I've got something in mind!",
                            "Sure! I'm thinking of something, and you have to guess what it is by asking yes or no questions. Go ahead and ask your first question!"
                        ]);
                    }
                    if (/(is it living|is it alive|is it a living thing)\b/.test(low)) {
                        return this._choose([
                            "Yes, it is living.",
                            "Yes, the thing I'm thinking of is living!"
                        ]);
                    }
                    if (/(is it a plant|is a plant|is this a plant)\b/.test(low)) {
                        return this._choose([
                            "No, it is not a plant.",
                            "No, the thing I'm thinking of is not a plant."
                        ]);
                    }
                    if (/(is it a mammal|is a mammal|is this a mammal)\b/.test(low)) {
                        return this._choose([
                            "Yes, it is a mammal.",
                            "Yes, the thing I'm thinking of is a mammal."
                        ]);
                    }
                    if (/(is it descended from wolves|is ancestor of wolves|is this descended from wolves)\b/.test(low)) {
                        return this._choose([
                            "Yes, it is descended from wolves.",
                            "Yes, the thing I'm thinking of is descended from wolves."
                        ]);
                    }
                    if (/(is it a dog|is a dog|is this a dog|is it a type of dog|is this a type of dog|is it a breed of dog|is this a breed of dog|is it a kind of dog)\b/.test(low)) {
                        return this._choose([
                            "Yes, it is a type of dog.",
                            "Yes, the thing I'm thinking of is a type of dog!"
                        ]);
                    }
                    if (/(is it a pug|is a pug|is this a pug)\b/.test(low)) {
                        return this._choose([
                            "Yes, it is a pug! Good job! You guessed it!",
                            "Yes, the thing I'm thinking of is a pug! You got it! 🐶"
                        ]);
                    }
                    if (/(can we play trivia|let's play trivia|want to play trivia|trivia)\b/.test(low)) {
                        return this._choose([
                            "Of course! How about dog trivia? I'll ask you a question about dogs, and you can try to answer it. Ready? Here's your first question: What breed of dog is known for its distinctive wrinkles and curly tail?",
                            "Sure, let's play trivia! I'll ask you a question about dogs, and you can try to answer it. Ready? Here's your first question: What breed of dog is known for its distinctive wrinkles and curly tail?"
                        ]);
                    }
                    if (/(a pug|it's a pug|it's a pug, right)\b/.test(low)) {
                        return this._choose([
                            "It is indeed a pug! Great guess! Pugs are such adorable dogs with their wrinkly faces and curly tails. 🐶 Here's another question: How many times better are dogs' sense of smell compared to humans?",
                            "Yes, it sure is a pug! Here's another question: How many times better are dogs' sense of smell compared to humans?"
                        ]);
                    }
                    if (/(100,000 times|100000 times|100,000 times better|100000 times better)\b/.test(low)) {
                        return this._choose([
                            "That's correct! Dogs' sense of smell is about 100,000 times better than humans. That's all the questions I have for now, but feel free to ask me anything else or we can play another game! 🐾",
                            "Yes! Dogs' sense of smell is about 100,000 times better than humans. That's all the questions I have for now, but feel free to ask me anything else or we can play another game! 🐾"
                        ]);
                    }
                    
                    if (/(what is 81 divided by 9|divide 81 by 9|81 divided by 9)\b/.test(low)) {
                        return this._choose([
                            "81 divided by 9 equals 9. You can think of it as splitting 81 into 9 equal parts, and each part would be 9.",
                            "The answer to 81 divided by 9 is 9. It's like sharing 81 cookies between 9 friends, and each friend gets 9 cookies!"
                        ]);
                    } 
                    if (/(what is 100 divided by 10|divide 100 by 10|100 divided by 10)\b/.test(low)) {
                        return this._choose([
                            "100 divided by 10 equals 10. You can think of it as splitting 100 into 10 equal parts, and each part would be 10.",
                            "The answer to 100 divided by 10 is 10. It's like sharing 100 cookies between 10 friends, and each friend gets 10 cookies!"
                        ]);
                    }       
                    if (/(what is 50 divided by 5|divide 50 by 5|50 divided by 5)\b/.test(low)) {
                        return this._choose([
                            "50 divided by 5 equals 10. You can think of it as splitting 50 into 5 equal parts, and each part would be 10.",
                            "The answer to 50 divided by 5 is 10. It's like sharing 50 cookies between 5 friends, and each friend gets 10 cookies!"
                        ]);
                    } 
                     if (/(what is 72 divided by 8|divide 72 by 8|72 divided by 8)\b/.test(low)) {
                        return this._choose([
                            "72 divided by 8 equals 9. You can think of it as splitting 72 into 8 equal parts, and each part would be 9.",
                            "The answer to 72 divided by 8 is 9. It's like sharing 72 cookies between 8 friends, and each friend gets 9 cookies!"
                        ]);
                    } 
                     if (/(what is 90 divided by 9|divide 90 by 9|90 divided by 9)\b/.test(low)) {
                        return this._choose([
                            "90 divided by 9 equals 10. You can think of it as splitting 90 into 9 equal parts, and each part would be 10.",
                            "The answer to 90 divided by 9 is 10. It's like sharing 90 cookies between 9 friends, and each friend gets 10 cookies!"
                        ]);
                    } 
                     if (/(what is half of fifty|half of fifty|50 divided by two|divide fifty by two|50 over two)\b/.test(low)) {
                        return this._choose([
                            "Half of fifty is twenty-five. You can think of it as splitting fifty into two equal parts, and each part would be twenty-five.",
                            "The answer to half of fifty is twenty-five. It's like sharing fifty cookies between two friends, and each friend gets twenty-five cookies!"
                        ]);
                    }          

                    if (/(what is 10 divided by 2|divide 10 by 2|10 divided by 2)\b/.test(low)) {
                        return this._choose([
                            "10 divided by 2 equals 5. You can think of it as splitting 10 into 2 equal parts, and each part would be 5.",
                            "The answer to 10 divided by 2 is 5. It's like sharing 10 cookies between 2 friends, and each friend gets 5 cookies!"
                        ]);
                    }
                    if (/(what is 15 divided by 3|divide 15 by 3|15 divided by 3)\b/.test(low)) {
                        return this._choose([
                            "15 divided by 3 equals 5. You can think of it as splitting 15 into 3 equal parts, and each part would be 5.",
                            "The answer to 15 divided by 3 is 5. It's like sharing 15 cookies between 3 friends, and each friend gets 5 cookies!"
                        ]);
                    }
                    if (/(what is 20 divided by 4|divide 20 by 4|20 divided by 4)\b/.test(low)) {
                        return this._choose([
                            "20 divided by 4 equals 5. You can think of it as splitting 20 into 4 equal parts, and each part would be 5.",
                            "The answer to 20 divided by 4 is 5. It's like sharing 20 cookies between 4 friends, and each friend gets 5 cookies!"
                        ]);
                    }
                    if (/(what is 53 divided by 4|divide 53 by 4|53 divided by 4)\b/.test(low)) {
                        return this._choose([
                            "53 divided by 4 equals 13.25. You can think of it as splitting 53 into 4 equal parts, and each part would be 13.25.",
                            "The answer to 53 divided by 4 is 13.25. It's like sharing 53 cookies between 4 friends, and each friend gets 13.25 cookies!"
                        ]);
                    }
                    if (/(what is 100 divided by 25|divide 100 by 25|100 divided by 25|100 over 25)\b/.test(low)) {
                        return this._choose([
                            "100 divided by 25 equals 4. You can think of it as splitting 100 into 25 equal parts, and each part would be 4.",
                            "The answer to 100 divided by 25 is 4. It's like sharing 100 cookies between 25 friends, and each friend gets 4 cookies!"
                        ]);
                    }
                     if (/(thanks for your help|thanks|thank you)\b/.test(low)) {
                        return this._choose([
                            "Anytime!",
                            "You're welcome! I'm always here to help.",
                            "No problem! I'm glad I could assist you."
                        ]);
                    }
                    if (/(what color is the sky|sky color|what is the sky's color)\b/.test(low)) {
                        return this._choose([
                            "The sky is blue!",
                            "The sky is typically blue, but it can look different at different times of day."
                        ]);
                    }
                    if (/(what color is grass|grass color|what is the grass's color)\b/.test(low)) {
                        return this._choose([
                            "Grass is green!",
                            "Grass is usually green, but it can turn brown when it's dry."
                        ]);
                    }
                     if (/(what does pug mean|pug definition|what is a pug|pug meaning)\b/.test(low)) {
                        return this._choose([
                            "A pug is a small dog breed known for its wrinkled face and curled tail.",
                            "A pug is a breed of dog that is small, sturdy, and has a distinctive wrinkled face."
                        ]);
                    }
                     if (/(what is a macbook|what is a MacBook|macbook|apple macbook|apple MacBook|MacBook)\b/.test(low)) {
                        return this._choose([
                            "A MacBook is a line of laptops designed and manufactured by Apple Inc. They are known for their sleek design, high performance, and user-friendly interface.",
                            "A MacBook is a type of laptop computer made by Apple. They are popular for their stylish design and powerful features, making them a favorite among students and professionals alike.",
                            "A MacBook is a laptop computer developed by Apple Inc. It runs on macOS and is known for its sleek design, high-quality build, and strong performance. MacBooks are popular among students, professionals, and creatives for their reliability and user-friendly interface.",
                            "A MacBook is a line of laptop computers designed and manufactured by Apple Inc. They are known for their sleek design, high performance, and user-friendly interface. MacBooks are popular among students, professionals, and creatives for their reliability and powerful features."
                        ]);
                    }
                     if (/(what ai model are you|what is your ai model|what ai model are you based on|what is your ai type)\b/.test(low)) {
                        return this._choose([
                            "I'm not really based on any AI model, but you can call me Rod AI.",
                            "I'm not really based on any AI model, but you can call me Rod AI! I'm just a fun chatbot designed to be your friendly pug companion. 🐶"
                        ]);
                    }
                    if (/(i love you|I love you so much|i love you soooooooo much)\b/.test(low)) {
                        return this._choose([
                            "Thank you! That's just like giving me a tasty treat! I love you too!🐾",
                            "That just made my day! Thank you! I love you too! 🐶"
                        ]);
                    }
                    if (/(dictionary|meanings|definitions)\b/.test(low)) {
                        return this._choose([
                            "I can be your dictionary! I don't know the meaning of every word, but I can try to help with common words. Just ask me for the definition of a word, and I'll do my best to explain it in a way that's easy to understand!",
                            "I can help with definitions! Just ask me for the meaning of a word, and I'll do my best to explain it in a simple way. I might not know every word, but I'll try my best to help you understand!"
                        ]);
                    }
                    if (/(dehydrator|dehydrator meaning|what is a dehydrator|define dehydrator|dehydrator definition)\b/.test(low)) {
                        return this._choose([
                            "A dehydrator is a device that removes moisture from food, preserving it for later consumption.",
                            "A dehydrator is a kitchen appliance used to remove water from fruits, vegetables, and other foods, helping to preserve them."
                        ]);
                    }
                    if (/(water|water meaning|what is water|define water|water definition)\b/.test(low)) {
                        return this._choose([
                            "Water is a transparent, tasteless, odorless liquid that is essential for life.",
                            "Water is a chemical compound made up of two hydrogen atoms and one oxygen atom."
                        ]);
                    }
                     if (/(what games can we play|games|can we play a game|what are some games we can play|what games are there that we can play)\b/.test(low)) {
                        return this._choose([
                            "We can play many games such as 20 Questions, Trivia, and maybe Word Fetch!"
                        ]);
                    }
                    if (/(what is your name|who are you)\b/.test(low)) {
                        return this._choose([
                            "I'm " + `${this.name}, your friendly pug assistant.`
                        ]);
                    }
                     if (/(word fetch|how about word fetch|can we play word fetch|let's play word fetch|what about word fetch)\b/.test(low)) {
                        return this._choose([
                            "Sure! Let's play Word Fetch! I'll give you a URL and you have to tell me the word in the website page. Here's your first one: https://wordfetch.rodthepug.com/#wordfetchp1 What word do you see on that page?"
                        ]);
                    }
                    if (/(supercalifragilisticexpialidocious|its supercalifragilisticexpialidocious|it's supercalifragilisticexpialidocious|the word is supercalifragilisticexpialidocious|it's supercalifragilisticexpialidocious, right)\b/.test(low)) {
                        return this._choose([
                            "Yes that's correct! Supercalifragilisticexpialidocious is the word! Great job! Here's another one: https://wordfetch.rodthepug.com/#wordfetchp2 What word do you see on that page?"
                        ]);
                    }
                    if (/(extraordinary|its extraordinary|it's extraordinary|the word is extraordinary|it's extraordinary, right)\b/.test(low)) {
                        return this._choose([
                            "Yes that's correct! Extraordinary is the word! Great job! Here's another one: https://wordfetch.rodthepug.com/#wordfetchp3 What word do you see on that page?"
                        ]);
                    }
                    if (/(window|its window|it's window|the word is window|it's window, right)\b/.test(low)) {
                        return this._choose([
                            "Yes that's correct! Window is the word! Great job! Here's another one: https://wordfetch.rodthepug.com/#wordfetchp4 What word do you see on that page?"
                        ]);
                    }
                    if (/(🐶|🐕|🦮|🐩|🐕‍🦺)\b/.test(low)) {
                        return this._choose([
                            "That's a dog emoji! I love dogs! 🐶",
                            "Woof! That's a dog emoji! I love dogs! 🐕",
                            "Yay, a dog emoji! I love dogs! 🐩",
                            "Woof woof! That's a dog emoji! I love dogs! 🦮",
                            "That's a dog emoji! I love dogs! 🐕‍🦺"
                        ]);
                    }
                    if (/(window|its window|it's window|the word is window|it's window, right)\b/.test(low)) {
                        return this._choose([
                            "Yes that's correct! Window is the word! Great job! Here's another one: https://wordfetch.rodthepug.com/#wordfetchp4 What word do you see on that page?"
                        ]);
                    }
                    if (/(stool|its stool|it's stool|the word is stool|it's stool, right)\b/.test(low)) {
                        return this._choose([
                            "Yes that's correct! Stool is the word! Great job! That's all the words I have for now, but feel free to ask me anything else or we can play another game! 🐾"
                        ]);
                    }
                    if (/(jigglypuff|whats jigglypuff|what's jigglypuff|jigglypuff pokemon|pokemon jigglypuff)\b/.test(low)) {
                        return this._choose([
                            "Jigglypuff is a Pokémon species in Nintendo and Game Freak's Pokémon franchise. It is a pink, balloon-like creature known for its ability to put others to sleep by singing a lullaby. Jigglypuff is a Normal/Fairy-type Pokémon and is often depicted as cute and cuddly, but it can be quite mischievous when its singing is not appreciated!"
                        ]);
                    }
                    if (/(who is billy joel|billy joel|who's billy joel)\b/.test(low)) {
                        return this._choose([
                            "Billy Joel is an American singer-songwriter and pianist, known for his hit songs like 'Piano Man' and 'We Didn't Start the Fire'. He has had a successful career spanning several decades and is considered one of the best-selling music artists of all time.",
                            "Billy Joel is a legendary American musician, singer-songwriter, and pianist. He is best known for his timeless hits such as 'Piano Man', 'Uptown Girl', and 'We Didn't Start the Fire'."
                        ]);
                    }
                    if (/(when is your birthday|what is your birthday|when were you born)\b/.test(low)) {
                        return this._choose([
                            "I don't have a birthday like humans do, but I was created by my developers at Rod AI. You could say my 'birthday' is the day I was launched! 🎉",
                            "I don't have a birthday like humans do, but I was created by my developers at Rod AI. You could say my 'birthday' is the day I was launched! 🐶"
                        ]);
                    }{
                    return this._choose([
                        "I don't know what that means. If you want help with something that I don't know yet, you can contact my developers at Rod AI and let them know what you'd like me to be able to do! In the meantime, maybe you can try asking me about something else or playing a game with me! 🐾"
                    ]);
                }
                // default playful transformations
                // echo with puppy flavor or provide a suggestion

                // otherwise playful echo + tip
            }

            _basicReplyTransform(s) {
                // simple transform to feel like a reply (non-copyright)
                const flipped = s.split('').reverse().join('');
                const short = s.length > 80 ? s.slice(0, 77) + '...' : s;
                return `I didn't catch that. I'm still learning, so I might not understand everything yet.`;
            }

            _randPersona() {
                return this.personality[Math.floor(Math.random() * this.personality.length)];
            }

            _choose(arr) {
                return arr[Math.floor(Math.random() * arr.length)];
            }
        }

        // UI wiring
        const chat = document.getElementById('chat');
        const input = document.getElementById('input');
        const sendBtn = document.getElementById('send');
        const puter = new Puter('Rod The Pug');

        function appendMessage(text, who='bot', meta='') {
            const wrap = document.createElement('div');
            wrap.className = 'msg ' + (who === 'me' ? 'me' : 'bot');
            const bubble = document.createElement('div');
            bubble.className = 'bubble';
            bubble.textContent = text;
            wrap.appendChild(bubble);
            if (meta) {
                const m = document.createElement('div');
                m.className = 'meta';
                m.textContent = meta;
                wrap.appendChild(m);
            }
            chat.appendChild(wrap);
            chat.scrollTop = chat.scrollHeight;
            return wrap;
        }

        function showTyping() {
            const t = document.createElement('div');
            t.className = 'msg bot typing-row';
            t.innerHTML = '<div class="bubble typing">Thinking…</div>';
            chat.appendChild(t);
            chat.scrollTop = chat.scrollHeight;
            return t;
        }

        async function sendMessage(text) {
            const trimmed = (text || '').trim();
            if (!trimmed) return;
            appendMessage(trimmed, 'me');
            input.value = '';
            // show typing indicator
            const typ = showTyping();
            // simulate thinking time proportional to length
            const delay = 400 + Math.min(2000, trimmed.length * 30);
            await new Promise(r => setTimeout(r, delay));
            const reply = await puter.getReply(trimmed);
            typ.remove();
            appendMessage(reply, 'bot', 'Rod The Pug');
        }

        sendBtn.addEventListener('click', () => sendMessage(input.value));
        input.addEventListener('keydown', e => {
            if (e.key === 'Enter') {
                e.preventDefault();
                sendMessage(input.value);
            }
        });

        // welcome message
        (async () => {
            appendMessage('Hi! I am Rod The Pug — your friendly furry companion. I can do many things, including telling jokes, sharing fun facts, and even helping with 3rd grade math homework!', 'bot', 'Rod The Pug');
        })();
    </script>a
</body>
</html>
