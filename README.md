# To-Do Goals Project

This repo is a code-along project for the React & Redux Course of the [React Nanodegree program](https://www.udacity.com/course/react-nanodegree--nd019).

## Project Setup
1. Go into the directory where the project now lives - `cd reactnd-redux-todos-goals`
2. Install the dependencies - `npm install`
3. Start the app - `npm start`

## Lesson Summary
<h5> How is state updated in Redux applications?</h5>
The whole goal of Redux is to increase predictability.
So far, our rules are:
<ol>
  <li>Only an event can change the state of the store.</li>
  <li>The function that returns the new state needs to be a pure function.</li>
</ol>
<h5>What are Pure Functions? </h5>

<p>Pure functions are integral to how state in Redux applications is updated. By definition, pure functions:</p>
<ol>
  <li>Return the same result if the same arguments are passed in </li>
  <li>Depend solely on the arguments passed into them </li>
  <li>Do not produce side effects, such as API requests and I/O operations </li>
</ol>

<p>Let’s check out an example of a pure function, <code>square()</code>:</p>
  <pre>
  <code class="lang-js"><span class="hljs-comment">// `square()` is a pure function</span>
  <span class="hljs-keyword">const</span> square = x =&gt; x * x;
  </code>
</pre>
square() is a pure function because it outputs the same value every single time, given that the same argument is passed into it. There is no dependence on any other values to produce that result, and we can safely expect just that result to be returned -- no side effects (more on this in a bit!).

On the other hand, let’s check out an example of an impure function, calculateTip():
<pre>
    <code class="lang-js">
    <span>// `calculateTip()` is an impure function</span>
    <span>const</span> tipPercentage = <span class="hljs-number">0.15</span>;
    <span>const</span> calculateTip = cost =&gt; cost * tipPercentage;
    </code>
</pre>
 

calculateTip() calculates and returns a number value. However, it relies on a variable (tipPercentage) that lives outside the function to produce that value. Since it fails one of the requirements of pure functions, calculateTip() is an impure function.

<p>Why Pure Functions Are Great</p>
For our purposes, the most important feature of a pure function is that it's predictable. If we have a function that takes in our state and an action that occurred, the function should (if it's pure!) return the exact same result every single time.

<h5>What is the store?</h5>
