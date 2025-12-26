# AI Usage

Briefly describe how you used AI (tools, prompts, code snippets, fixes). Be concise and honest (using AI is fine; it's just a tool; we want to know your method). If you did not use AI, state that here.

I used AI (ChatGPT) only a few times, first to help clone the project to my GitHub and set it to connect only my repository.
Second time to figure out how to get the loanToNextAllowed() method to work. At first I tried an enhanced for-loop, but got an error. As ChatGPT explained, it was a ConcurrentModificationException because I tried to change the collection I was iterating. ChatGPT suggested using an Iterator and iterator.remove() instead.

I intentionally didn't want to use AI for quick results, to gain more knowledge by myself. Totally it took about 8-10 hours.

After i did finish my changes, i let ChatGPT (codex) to analyse my solution and it brought out some points.
1. borrowBook() didnt check for queue. Althou i find it unfair to other readers to keep book reserved to reader who is overloaned, because it is only way queue to form, if reader who is loaned already maximum alowed books reserve free book, and it wont automatically loaned out because of max limit. To comply what said in Readme (If a reservation queue exists, only the head of the queue should receive the book (no line-jumping via direct borrow).) i added queue check to borrow method.
2. reserveBook() also didnt check for queue, so i added it.
3. loanToNextAlowed() wont remove ineligible/missing, but it skips them and removes first eligible who gets the book from queue, so keeps queue consistent. So i didnt change anything.