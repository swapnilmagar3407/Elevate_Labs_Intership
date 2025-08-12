# Task 6: Create a Strong Password and Evaluate Its Strength

## Objective
Understand what makes a password strong and test it against password strength tools.

## Tools
- Online password strength checkers (e.g., passwordmeter.com) — (Note: results here are example/simulated so you can paste into tools yourself.)
- This report files bundle for GitHub submission.

## Passwords Created (varying complexity)
1. `password123`  
   - Type: Common word + numbers  
   - Expected strength: Very weak  
   - Reason: Common word, predictable, short.

2. `Passw0rd!`  
   - Type: Mixed case + number + symbol  
   - Expected strength: Weak to moderate  
   - Reason: Uses variety but resembles the common word "password".

3. `S@feH0use2025`  
   - Type: Mixed case + symbols + numbers, length 12  
   - Expected strength: Strong  
   - Reason: Longer, mixes character classes, not a single dictionary word.

4. `7&gF#9vQ!kLz`  
   - Type: Random characters, length 12  
   - Expected strength: Very strong  
   - Reason: High entropy, no dictionary words, multiple character classes.

5. `ILovePizza!!2025`  
   - Type: Phrase-like with punctuation + numbers  
   - Expected strength: Moderate to strong (depends on checker)  
   - Reason: Contains a phrase (guessable for social-engineering) but has length and symbols.

## How I Tested (instructions for you to reproduce)
1. Open a password strength checker such as `https://www.passwordmeter.com` or any other trusted site.
2. Copy each test password from above into the checker.
3. Note the score, estimated time-to-crack (if provided), and feedback for each password.
4. Record the results in a simple table (or use the included `results.md` file to paste your findings).

## Example (Simulated) Results Table
| Password | Length | Character Classes | Example Strength | Why |
|---|---:|---:|---|---|
| password123 | 11 | lowercase + digits | Very weak | Common word + digits; guessable. |
| Passw0rd! | 9 | upper + lower + digits + symbol | Weak | Variation of "password" is common. |
| S@feH0use2025 | 12 | upper + lower + digits + symbol | Strong | Longer and diverse classes, less guessable. |
| 7&gF#9vQ!kLz | 12 | mixed random | Very strong | High entropy; not based on words. |
| ILovePizza!!2025 | 16 | upper + lower + digits + symbol | Moderate-Strong | Long and diverse but contains a guessable phrase. |

> **Note:** Real tool outputs may differ slightly; always test live and adjust.

## Common Password Attacks (brief)
- **Brute-force attack**: Tries every possible combination. Time-to-crack grows exponentially with length and character set size.
- **Dictionary attack**: Uses lists of common passwords and words (very effective against short or common-word passwords).
- **Hybrid attacks**: Combine dictionary words with common substitutions (e.g., `@` for `a`) or appended numbers.
- **Credential stuffing**: Reuse of leaked username/password pairs across sites.

## Best Practices & Tips
- Use a minimum of 12 characters for important accounts.
- Combine uppercase, lowercase, numbers, and symbols.
- Avoid single dictionary words or obvious substitutions (e.g., `P@ssw0rd` is weak).
- Prefer long passphrases made of unrelated words or a random password generator.
- Use a reputable password manager to store unique passwords per site.
- Enable multi-factor authentication (MFA) wherever possible.

## Summary / Conclusion
Password strength is primarily about **entropy** — length plus unpredictability. Increasing length and using a wide variety of character classes increases the time required for an attacker to crack a password. Always use unique passwords per service and protect accounts with MFA.

---

**Files included in this repository:**
- `report.md` — This report (you are reading it).
- `README.md` — Instructions and description for GitHub.
- `results.md` — A placeholder file to paste your live tool test results.
- `password_examples.txt` — Plain text list of example passwords (for testing).
