---
title       : Risk Calculator
subtitle    : 
author      : What2do
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
## Introduction

This Risk Calculator aims to illustrate how our annual insurance premium is calculated.
The current app uses 3 risk factors: cigarette, occupation and pre-existing condition.

Based on the 3 factors the app will then compute a risk index and will multiply the existing premiums with the index.

The app will then show the respective premium for the gender selected and for current age bracket onwards.

--- 
## Inputs used to calculate your risk

<div class="row-fluid">
  <div class="col-sm-4">
    <form class="well">
      <div class="form-group shiny-input-container">
        <label class="control-label" for="cigarette">Number of cigarette you smoke a day:</label>
        <div>
          <select id="cigarette"><option value="0" selected>0</option>
<option value="1-3">1-3</option>
<option value="4-5">4-5</option>
<option value="&gt;5">&gt;5</option></select>
          <script type="application/json" data-for="cigarette" data-nonempty="">{}</script>
        </div>
      </div>
      <br/>
      <div class="form-group shiny-input-container">
        <label class="control-label" for="occupation">Your Occupation:</label>
        <div>
          <select id="occupation"><option value="Office" selected>Office</option>
<option value="Sales">Sales</option>
<option value="Construction">Construction</option></select>
          <script type="application/json" data-for="occupation" data-nonempty="">{}</script>
        </div>
      </div>
      <br/>
      <div class="form-group shiny-input-container">
        <div class="checkbox">
          <label>
            <input id="preexistingcondition" type="checkbox"/>
            <span>Do you have any pre-existing condition?</span>
          </label>
        </div>
      </div>
      <br/>
      <span class="help-block">Note: The calculator will base on the inputs provided above to compute a risk index and work out the premium rates to pay from the current age band onwards.</span>
    </form>
  </div>
  <div class="col-sm-8">
    <h2>
      <div id="displayname" class="shiny-text-output"></div>
    </h2>
  </div>
</div>

---

## How it works

For each of the risk factors shown in front:
1. Cigarette
2. Occupation
3. Pre-existing condition

There is risk weightage (e.g. cigarette "0" = 0, "1-3" = 0.1, "4-5" = 0.3, ">5" = 0.5)  

The App will sum the risk weigtage for all 3 factors to be the overall risk index.

Finally, the original premium amount will be multiplied by this index to give you the actual premium ("loaded" amount).

---
## Run App from Shiny

<iframe src="http://what2do.shinyapps.io/riskcalculator2"></iframe>




