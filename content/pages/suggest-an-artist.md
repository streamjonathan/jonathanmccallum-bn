---
title: "একজন শিল্পীর নাম জানান"
slug: suggest-an-artist
---

যীশুকে অনুসরণ করেন এমন সংগীতশিল্পী ও শিল্পীদের কথা শুনতে আমার খুব ভালো লাগে। আপনি যদি এমন কাউকে চেনেন যাঁর সম্পর্কে আমি লিখব, যাঁর সাক্ষাৎকার নেব বা যাঁর সম্পর্কে প্রতিক্রিয়া ভিডিও বানাব, তাহলে এখানে আমাকে জানান।

একটি নাম আর একটি লিংকই যথেষ্ট — আর কেন তিনি, কয়েকটি শব্দে। যা আসে, আমি সব পড়ি। অনেক ধন্যবাদ।

এঁদের কাউকে কি চেনেন? ছবিতে চাপ দিন, ফর্মটি নিজে থেকেই ভরে যাবে — তারপর কয়েকটি শব্দে জানান কেন তিনি, আর পাঠিয়ে দিন।

<div class="suggest-carousel" role="list" aria-label="যেসব সংগীতশিল্পী ও শিল্পীর নাম আপনি জানাতে পারেন">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="{{ artist.name }}-এর নাম জানান">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">অথবা নিচে নতুন কারও নাম জানান — যাঁর কথা আমার শোনা উচিত বলে আপনার মনে হয়।</p>

এই সাইটটি ১৮ বছরের কম বয়সীদের জন্য নয়।

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">শিল্পীর নাম</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="আমি কাকে দেখব?" required>

  <label for="suggest-link">সোশ্যাল মিডিয়া প্রোফাইলের লিংক</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>তাঁকে নিয়ে আমি কী করব?</legend>
    <label><input type="checkbox" name="kind" value="write"> তাঁর সম্পর্কে লিখব</label>
    <label><input type="checkbox" name="kind" value="interview"> তাঁর সাক্ষাৎকার নেব</label>
    <label><input type="checkbox" name="kind" value="reaction"> তাঁর সম্পর্কে প্রতিক্রিয়া ভিডিও বানাব</label>
  </fieldset>

  <label for="suggest-why">কেন তিনি?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="কয়েকটি শব্দই যথেষ্ট…"></textarea>

  <label for="suggest-name">আপনার নাম <span class="optional">(ঐচ্ছিক)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="যাতে আমি আপনাকে ধন্যবাদ জানাতে পারি">

  <label for="suggest-from-link">আপনার সোশ্যাল মিডিয়া প্রোফাইলের লিংক <span class="optional">(ঐচ্ছিক)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">পরামর্শ পাঠান</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
