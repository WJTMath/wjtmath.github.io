---
title: MyOpenMath Tools
sidebar:
  nav: home
---

I use these links to help me debug questions on [MyOpenMath](https://www.myopenmath.com/).

<form>
<input type="number" id="qid" placeholder="Question ID" oninput="updateLinks()">
<input type="number" id="sid" placeholder="Optional: Seed ID" oninput="updateLinks()">
</form>

<a id="previewLink"></a>

<a id="codeViewLink"></a>

<a id="embedLink"></a>

<script>
  const previewEl = document.querySelector('#previewLink');
  const codeViewEl = document.querySelector('#codeViewLink');
  const embedEl = document.querySelector('#embedLink');
  const qidEl = document.querySelector('#qid');
  const sidEl =  document.querySelector('#sid');
  function updateLinks() {
    let qid = qidEl.valueAsNumber;
    let sid = sidEl.valueAsNumber;
    // javascript:{let t=prompt('Preview: Enter QID.');if(null!=t){let e=window.open('https://www.myopenmath.com/course/testquestion2.php?qsetid='+t,'_blank')}}
    // javascript:{let t=prompt('View Code: Enter QID.');if(null!=t){let e=window.open('https://www.myopenmath.com/course/moddataset.php?id='+t,'_blank')}}
    // javascript:{let p=prompt('Embed: Enter QID.');if(null!=p){let e=window.open('https://www.myopenmath.com/embedq2.php?id='+p,'_blank')}}
    previewEl.innerText = 'Question Preview, QID #'+(qid ? qid : '??');
    codeViewEl.innerText = 'Code View, QID #'+(qid ? qid : '??');
    embedEl.innerText = 'Embed View, QID #'+(qid ? qid : '??');
    if (sid) previewEl.innerText += ', Seed #'+sid;
    if (qid) {
      previewEl.href = 'https://www.myopenmath.com/course/testquestion2.php?qsetid='+qid+(sid ? '&seed='+sid : '')
      codeViewEl.href = 'https://www.myopenmath.com/course/moddataset.php?id='+qid;
      embedEl.href = 'https://www.myopenmath.com/embedq2.php?id='+qid;
      [previewEl, codeViewEl, embedEl].forEach((e) => {
        e.target = '_blank';
      });
    } else {
      previewEl.href = 'javascript:{qidPrompt(previewEl);}';
      codeViewEl.href = 'javascript:{qidPrompt(codeViewEl);}';
      embedEl.href = 'javascript:{qidPrompt(embedEl);}';
      [previewEl, codeViewEl, embedEl].forEach((e) => {
        e.target = '';
      });
    }
  }
  function qidPrompt(el) {
    console.log(el);
    let qid = qidEl.valueAsNumber;
    if (!qid) qid = Number(prompt('Preview: Enter Question ID'));
    if (qid) {
      qidEl.valueAsNumber = qid;
      updateLinks();
      el.click();
    } else {
      alert('Invalid entry. Aborting.');
    }
  }
  updateLinks();
</script>