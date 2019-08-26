---
title: Eth2 hello!
description: 
published: true
date: 2019-08-26T05:47:32.290Z
tags: 
---

<script src="https://underscorejs.org/underscore-min.js"></script>
<script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
<script src="https://d3js.org/d3.v4.min.js"></script>
<script crossorigin src="https://hackingresear.ch/libs/cbc.js"></script>
<script crossorigin src="https://hackingresear.ch/src/component-library.js"></script>
<script crossorigin src="https://hackingresear.ch/src/components/cbc-components.js"></script>

<div class="i-visual" id="clique-visual"></div>
<script>
  console.log("hello");
      ReactDOM.render(
        e(
          InteractiveFigure, {
            name: "A complete bipartite graph of 4 validators.",
            caption: e(
              "div", null,
              "Each row contains messages by one validator, indexed on the left. The 4 validators agree on the consensus value, Blue. Additionally, they all send an extra message justified by all 4 first messages, so they all acknowledge that they agree. We look for such patterns to determine the finality of a decision. ",
              e("br", null),
              e(
                "span", { className: "caption-interaction-explanation" },
                "> Hover above a circle to reveal the messages in its justification. Latest messages are revealed by an orange ring around the circle."
              )
            )
          },
          e(
            ValidatorDAGVisual, {
              elementId: "clique-visual",
              height: 300,
              data: cbc.makeClique(4),
              circleRadius: 6,
              edgeOpacity: 1
            }
          )
        ),
        document.querySelector('#clique-visual')
      )
</script>

# Header

Your content here
