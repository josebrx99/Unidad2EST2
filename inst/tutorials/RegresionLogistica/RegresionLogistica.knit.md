---
title: "**REGRESIÓN LOGÍSTICA**"
author: Modelos estadísticos para la toma de decisiones
output: 
  learnr::tutorial:
    css: css/learnr_metadocencia.css
    progressive: true # los encabezados de tercer nivel (###) son revelados progresivamente
    allow_skip: true # permite saltearse los ejercicios. 
    language:
      es: tutorial_es.json
description: "Tutorial interactivo conceptos básicos de probabilidad" # Esta descripción se ve en el panel Tutorial de RStudio 
runtime: shiny_prerendered
---



## **PRESENTACIÓN**

El presente tutorial contiene preguntas relacionadas con la regresión logística.

</br>

## **CUESTIONARIO**

### **Pregunta 1**


```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q1-1" class="tutorial-question panel-body">
<div id="q1-1-answer_container" class="shiny-html-output"></div>
<div id="q1-1-message_container" class="shiny-html-output"></div>
<div id="q1-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```

### **Pregunta 2**


```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q2-1" class="tutorial-question panel-body">
<div id="q2-1-answer_container" class="shiny-html-output"></div>
<div id="q2-1-message_container" class="shiny-html-output"></div>
<div id="q2-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```

### **Pregunta 3**


```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q3-1" class="tutorial-question panel-body">
<div id="q3-1-answer_container" class="shiny-html-output"></div>
<div id="q3-1-message_container" class="shiny-html-output"></div>
<div id="q3-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```

### **Pregunta 4**


```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q4-1" class="tutorial-question panel-body">
<div id="q4-1-answer_container" class="shiny-html-output"></div>
<div id="q4-1-message_container" class="shiny-html-output"></div>
<div id="q4-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```

### **Pregunta 5**


```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q5-1" class="tutorial-question panel-body">
<div id="q5-1-answer_container" class="shiny-html-output"></div>
<div id="q5-1-message_container" class="shiny-html-output"></div>
<div id="q5-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```

### **Pregunta 6**


```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q6-1" class="tutorial-question panel-body">
<div id="q6-1-answer_container" class="shiny-html-output"></div>
<div id="q6-1-message_container" class="shiny-html-output"></div>
<div id="q6-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```


## **PROBLEMAS**

### **Problema 1**
Este tutorial cuenta con la base de datos "creditos" (la cual se puede acceder mediante la función data("creditos")), se cuenta con 780 registros de clientes que pidieron prestamos a una entidad bancaria, se tienen las variables:
<div>
  <ul>
    <li> **DEFAULT:** indica si el cliente resultó moroso en las cuotas de su crédito, 1 indica que si y 0 que no.</li>
    <li> **ANTIGUEDAD:** años que ha pertenecido el cliente en la entidad.</li>
    <li> **CUOTA_TOTAL:** monto total del prestamo en pesos colombianos.</li>
    <li> **INGRESOS:** ingresos mensuales del cliente en pesos colombianos.</li>
  </ul>
</div>

Se quiere realizar un modelo de regresión logistico en donde se pueda predecir la probabilidad de que una persona resulte morosa.

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":["precio"],"name":[1],"type":["dbl"],"align":["right"]},{"label":["calorias"],"name":[2],"type":["dbl"],"align":["right"]},{"label":["poralcoh"],"name":[3],"type":["dbl"],"align":["right"]}],"data":[{"1":"6.24","2":"159","3":"5.2"},{"1":"4.79","2":"160","3":"5.0"},{"1":"5.96","2":"160","3":"4.9"},{"1":"4.70","2":"162","3":"4.9"},{"1":"4.11","2":"157","3":"5.5"},{"1":"3.85","2":"151","3":"4.9"},{"1":"2.52","2":"155","3":"4.7"},{"1":"5.46","2":"135","3":"5.1"},{"1":"6.00","2":"162","3":"5.4"},{"1":"3.71","2":"142","3":"4.8"},{"1":"6.70","2":"146","3":"4.4"},{"1":"4.99","2":"148","3":"4.3"},{"1":"4.10","2":"170","3":"5.1"},{"1":"5.96","2":"160","3":"5.0"},{"1":"6.31","2":"172","3":"5.8"},{"1":"6.42","2":"170","3":"5.9"},{"1":"7.79","2":"184","3":"6.0"},{"1":"5.05","2":"201","3":"5.6"},{"1":"5.26","2":"155","3":"4.7"},{"1":"5.84","2":"170","3":"5.3"},{"1":"7.22","2":"158","3":"4.9"},{"1":"6.12","2":"159","3":"5.4"},{"1":"7.37","2":"150","3":"5.1"},{"1":"6.47","2":"177","3":"5.6"},{"1":"6.72","2":"146","3":"3.7"},{"1":"7.59","2":"151","3":"4.9"},{"1":"6.36","2":"163","3":"5.3"},{"1":"6.52","2":"186","3":"5.9"},{"1":"6.34","2":"168","3":"5.9"},{"1":"7.10","2":"142","3":"4.7"},{"1":"4.78","2":"148","3":"5.0"},{"1":"4.63","2":"150","3":"5.0"},{"1":"5.41","2":"140","3":"5.0"},{"1":"6.39","2":"150","3":"5.0"},{"1":"5.52","2":"160","3":"4.8"},{"1":"6.38","2":"160","3":"5.0"},{"1":"5.68","2":"148","3":"4.6"},{"1":"5.82","2":"148","3":"4.9"},{"1":"5.83","2":"148","3":"4.3"},{"1":"7.80","2":"160","3":"4.1"},{"1":"2.82","2":"145","3":"4.5"},{"1":"3.20","2":"142","3":"4.4"},{"1":"3.83","2":"147","3":"5.0"},{"1":"4.02","2":"148","3":"4.9"},{"1":"3.88","2":"149","3":"5.5"},{"1":"4.79","2":"155","3":"5.6"},{"1":"4.00","2":"159","3":"5.0"},{"1":"3.95","2":"148","3":"5.5"},{"1":"3.27","2":"143","3":"4.9"},{"1":"4.02","2":"137","3":"4.6"},{"1":"3.26","2":"153","3":"4.6"},{"1":"3.19","2":"143","3":"5.0"},{"1":"2.90","2":"144","3":"4.7"},{"1":"2.36","2":"133","3":"4.6"},{"1":"3.93","2":"143","3":"5.0"},{"1":"4.25","2":"143","3":"4.6"},{"1":"4.03","2":"134","3":"4.3"},{"1":"4.02","2":"110","3":"4.2"},{"1":"2.86","2":"110","3":"4.2"},{"1":"4.03","2":"105","3":"4.2"},{"1":"4.02","2":"96","3":"4.5"},{"1":"6.49","2":"95","3":"3.6"},{"1":"3.24","2":"58","3":"0.0"},{"1":"3.60","2":"82","3":"0.0"},{"1":"2.99","2":"60","3":"0.0"},{"1":"2.75","2":"72","3":"0.0"},{"1":"3.90","2":"70","3":"0.0"},{"1":"5.42","2":"71","3":"0.0"},{"1":"5.63","2":"96","3":"0.0"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>
</div>



### **Problema 1.1**
**Realice un análisis exploratorio de las variables mediante la función plot.**

<div class="tutorial-exercise" data-label="p0" data-completion="1" data-diagnostics="1" data-startover="1" data-lines="5"><script type="application/json" data-ui-opts="1">{"engine":"r","has_checker":false,"caption":"<span data-i18n=\"text.enginecap\" data-i18n-opts=\"{&quot;engine&quot;:&quot;R&quot;}\">R Code<\/span>"}</script></div>
<div class="tutorial-exercise-support" data-label="p0-hint" data-completion="1" data-diagnostics="1" data-startover="1" data-lines="0">

```text
plot()
```

</div>
<div class="tutorial-exercise-support" data-label="p0-solution" data-completion="1" data-diagnostics="1" data-startover="1" data-lines="0">

```text
plot(creditos)
```

</div>


### **Problema 1.2*
**Calcule el modelo logistico con todas la covariables y muestre el resumen de este (summary).**
<div class="tutorial-exercise" data-label="p1" data-completion="1" data-diagnostics="1" data-startover="1" data-lines="5"><script type="application/json" data-ui-opts="1">{"engine":"r","has_checker":false,"caption":"<span data-i18n=\"text.enginecap\" data-i18n-opts=\"{&quot;engine&quot;:&quot;R&quot;}\">R Code<\/span>"}</script></div>
<div class="tutorial-exercise-support" data-label="p1-hint" data-completion="1" data-diagnostics="1" data-startover="1" data-lines="0">

```text
modelo = glm(DEFAULT ~ ,family=binomial(link="logit"), data= )
```

</div>
<div class="tutorial-exercise-support" data-label="p1-solution" data-completion="1" data-diagnostics="1" data-startover="1" data-lines="0">

```text
modelo = glm(DEFAULT ~ ANTIUEDAD + EDAD + CUOTA_TOTAL + INGRESOS,family=binomial(link="logit"), data= creditos)
summary(modelo)
```

</div>

### **Problema 1.3**

```{=html}
<div class="panel-heading tutorial-quiz-title"></div>
```

```{=html}
<div class="panel panel-default tutorial-question-container">
<div data-label="q7-1" class="tutorial-question panel-body">
<div id="q7-1-answer_container" class="shiny-html-output"></div>
<div id="q7-1-message_container" class="shiny-html-output"></div>
<div id="q7-1-action_button_container" class="shiny-html-output"></div>
<script>if (Tutorial.triggerMathJax) Tutorial.triggerMathJax()</script>
</div>
</div>
```












preservedb763a8697a8eb2f
preserve49a5549c4e0167a4
preserve99511dba600bfa45
preserve5ca03768833e32d9
preserve51bc945c9c85971f
preserve32041485cdd21b00
preserve186a184f38777487
preserve456c4bbf75421632
preserve765843471743c0b6
preserve465a8e6d2edc1d14
preserve7b397ef8a9c4eac3
preserveb6ccdce3a4d69bc2
preserve271d9167fd7f7b28
preservece4b1b0ad420b83b
preserve12ea1fed2ef9c6dc
preserve7291476ec8970a99

<!--html_preserve-->
<script type="application/shiny-prerendered" data-context="dependencies">
{"type":"list","attributes":{},"value":[{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["header-attrs"]},{"type":"character","attributes":{},"value":["2.21"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmd/h/pandoc"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["header-attrs.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["rmarkdown"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["2.21"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["jquery"]},{"type":"character","attributes":{},"value":["3.6.0"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/3.6.0"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["jquery-3.6.0.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["jquerylib"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.1.4"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["bootstrap"]},{"type":"character","attributes":{},"value":["3.3.5"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmd/h/bootstrap"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["viewport"]}},"value":[{"type":"character","attributes":{},"value":["width=device-width, initial-scale=1"]}]},{"type":"character","attributes":{},"value":["js/bootstrap.min.js","shim/html5shiv.min.js","shim/respond.min.js"]},{"type":"character","attributes":{},"value":["css/cerulean.min.css"]},{"type":"character","attributes":{},"value":["<style>h1 {font-size: 34px;}\n       h1.title {font-size: 38px;}\n       h2 {font-size: 30px;}\n       h3 {font-size: 24px;}\n       h4 {font-size: 18px;}\n       h5 {font-size: 16px;}\n       h6 {font-size: 12px;}\n       code {color: inherit; background-color: rgba(0, 0, 0, 0.04);}\n       pre:not([class]) { background-color: white }<\/style>"]},{"type":"NULL"},{"type":"character","attributes":{},"value":["rmarkdown"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["2.21"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["pagedtable"]},{"type":"character","attributes":{},"value":["1.1"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmd/h/pagedtable-1.1"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["js/pagedtable.js"]},{"type":"character","attributes":{},"value":["css/pagedtable.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["rmarkdown"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["2.21"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["highlightjs"]},{"type":"character","attributes":{},"value":["9.12.0"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmd/h/highlightjs"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["highlight.js"]},{"type":"character","attributes":{},"value":["textmate.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["rmarkdown"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["2.21"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["tutorial"]},{"type":"character","attributes":{},"value":["0.11.3"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/tutorial"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["tutorial.js"]},{"type":"character","attributes":{},"value":["tutorial.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["i18n"]},{"type":"character","attributes":{},"value":["21.6.10"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/i18n"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["i18next.min.js","tutorial-i18n-init.js"]},{"type":"NULL"},{"type":"character","attributes":{},"value":["<script id=\"i18n-cstm-trns\" type=\"application/json\">{\"language\":\"es\",\"resources\":{\"en\":{\"translation\":{\"button\":{\"runcode\":\"Run Code\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Hint\",\"hint_plural\":\"Hints\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Next Hint\",\"hintprev\":\"Previous Hint\",\"solution\":\"Solution\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Copy to Clipboard\",\"startover\":\"Start Over\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Continue\",\"submitanswer\":\"Submit Answer\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Previous Topic\",\"nexttopic\":\"Next Topic\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Try Again\"},\"text\":{\"startover\":\"Start Over\",\"areyousure\":\"Are you sure you want to start over? (all exercise progress will be reset)\",\"youmustcomplete\":\"You must complete the\",\"exercise\":\"exercise\",\"exercise_plural\":\"exercises\",\"inthissection\":\"in this section before continuing.\",\"code\":\"Code\",\"enginecap\":\"{{engine}} $t(text.code)\",\"quiz\":\"Quiz\",\"blank\":\"blank\",\"blank_plural\":\"blanks\",\"exercisecontainsblank\":\"This exercise contains {{count}} $t(text.blank).\",\"pleasereplaceblank\":\"Please replace {{blank}} with valid code.\",\"unparsable\":\"It looks like this might not be valid R code. R cannot determine how to turn your text into a complete command. You may have forgotten to fill in a blank, to remove an underscore, to include a comma between arguments, or to close an opening <code>&quot;<\\/code>, <code>'<\\/code>, <code>(<\\/code> or <code>{<\\/code> with a matching <code>&quot;<\\/code>, <code>'<\\/code>, <code>)<\\/code> or <code>}<\\/code>.\\n\",\"unparsablequotes\":\"<p>It looks like your R code contains specially formatted quotation marks or &quot;curly&quot; quotes (<code>{{character}}<\\/code>) around character strings, making your code invalid. R requires character values to be contained in straight quotation marks (<code>&quot;<\\/code> or <code>'<\\/code>).<\\/p> {{code}} <p>Don't worry, this is a common source of errors when you copy code from another app that applies its own formatting to text. You can try replacing the code on that line with the following. There may be other places that need to be fixed, too.<\\/p> {{suggestion}}\\n\",\"unparsableunicode\":\"<p>It looks like your R code contains an unexpected special character (<code>{{character}}<\\/code>) that makes your code invalid.<\\/p> {{code}} <p>Sometimes your code may contain a special character that looks like a regular character, especially if you copy and paste the code from another app. Try deleting the special character from your code and retyping it manually.<\\/p>\\n\",\"unparsableunicodesuggestion\":\"<p>It looks like your R code contains an unexpected special character (<code>{{character}}<\\/code>) that makes your code invalid.<\\/p> {{code}} <p>Sometimes your code may contain a special character that looks like a regular character, especially if you copy and paste the code from another app. You can try replacing the code on that line with the following. There may be other places that need to be fixed, too.<\\/p> {{suggestion}}\\n\",\"and\":\"and\",\"or\":\"or\",\"listcomma\":\", \",\"oxfordcomma\":\",\"}}},\"fr\":{\"translation\":{\"button\":{\"runcode\":\"Lancer le Code\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Indication\",\"hint_plural\":\"Indications\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Indication Suivante\",\"hintprev\":\"Indication Précédente\",\"solution\":\"Solution\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Copier dans le Presse-papier\",\"startover\":\"Recommencer\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Continuer\",\"submitanswer\":\"Soumettre\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Chapitre Précédent\",\"nexttopic\":\"Chapitre Suivant\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Réessayer\"},\"text\":{\"startover\":\"Recommencer\",\"areyousure\":\"Êtes-vous certains de vouloir recommencer? (La progression sera remise à zéro)\",\"youmustcomplete\":\"Vous devez d'abord compléter\",\"exercise\":\"l'exercice\",\"exercise_plural\":\"des exercices\",\"inthissection\":\"de cette section avec de continuer.\",\"code\":\"Code\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Quiz\",\"and\":\"et\",\"or\":\"ou\",\"oxfordcomma\":\"\"}}},\"es\":{\"translation\":{\"button\":{\"runcode\":\"Ejecutar código\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Pista\",\"hint_plural\":\"Pistas\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Siguiente pista\",\"hintprev\":\"Pista anterior\",\"solution\":\"Solución\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Copiar al portapapeles\",\"startover\":\"Reiniciar\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Continuar\",\"submitanswer\":\"Enviar respuesta\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Tema anterior\",\"nexttopic\":\"Tema siguiente\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Volver a intentar\"},\"text\":{\"startover\":\"Reiniciar\",\"areyousure\":\"¿De verdad quieres empezar de nuevo? (todo el progreso del ejercicio se perderá)\",\"youmustcomplete\":\"Debes completar\",\"exercise\":\"el ejercicio\",\"exercise_plural\":\"los ejercicios\",\"inthissection\":\"en esta sección antes de continuar.\",\"code\":\"Código\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Cuestionario\",\"and\":\"y\",\"or\":\"o\",\"oxfordcomma\":\"\"}},\"custom\":{\"button\":{\"runcode\":\"Ejecutar\",\"hints\":\"Pistas\",\"startover\":\"Reiniciar\",\"continue\":\"Continuar\",\"submitanswer\":\"Enviar respuesta\",\"previoustopic\":\"Tema anterior\",\"nexttopic\":\"Siguiente tema\",\"questionsubmit\":\"Enviar respuesta\",\"questiontryagain\":\"Intentar de nuevo\"},\"text\":{\"startover\":\"Empezar de nuevo\",\"areyousure\":\"¿Estás segure que querés reiniciar? (se perderá todo el progreso)\",\"youmustcomplete\":\"Tienes que completar\",\"exercise\":\"el ejercicio\",\"exercise_plural\":\"los ejercicios\",\"inthissection\":\"en esta sección antes de continuar\"}}},\"pt\":{\"translation\":{\"button\":{\"runcode\":\"Executar código\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Dica\",\"hint_plural\":\"Dicas\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Próxima dica\",\"hintprev\":\"Dica anterior\",\"solution\":\"Solução\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Copiar para a área de transferência\",\"startover\":\"Reiniciar\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Continuar\",\"submitanswer\":\"Enviar resposta\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Tópico anterior\",\"nexttopic\":\"Próximo tópico\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Tentar novamente\"},\"text\":{\"startover\":\"Reiniciar\",\"areyousure\":\"Tem certeza que deseja começar novamente? (todo o progresso feito será perdido)\",\"youmustcomplete\":\"Você deve completar\",\"exercise\":\"o exercício\",\"exercise_plural\":\"os exercícios\",\"inthissection\":\"nesta seção antes de continuar.\",\"code\":\"Código\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Quiz\",\"and\":\"e\",\"or\":\"ou\",\"oxfordcomma\":\"\"}}},\"tr\":{\"translation\":{\"button\":{\"runcode\":\"Çalıştırma Kodu\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Ipucu\",\"hint_plural\":\"İpuçları\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Sonraki İpucu\",\"hintprev\":\"Önceki İpucu\",\"solution\":\"Çözüm\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Pano'ya Kopyala\",\"startover\":\"Baştan Başlamak\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Devam et\",\"submitanswer\":\"Cevabı onayla\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Önceki Konu\",\"nexttopic\":\"Sonraki Konu\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Tekrar Deneyin\"},\"text\":{\"startover\":\"Baştan Başlamak\",\"areyousure\":\"Baştan başlamak istediğinizden emin misiniz? (tüm egzersiz ilerlemesi kaybolacak)\",\"youmustcomplete\":\"Tamamlamalısın\",\"exercise\":\"egzersiz\",\"exercise_plural\":\"egzersizler\",\"inthissection\":\"devam etmeden önce bu bölümde\",\"code\":\"Kod\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Sınav\",\"oxfordcomma\":\"\"}}},\"emo\":{\"translation\":{\"button\":{\"runcode\":\"🏃\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"💡\",\"hint_plural\":\"$t(button.hint)\",\"hinttitle\":\"$t(button.hint)\",\"solution\":\"🎯\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"📋\",\"startover\":\"⏮\",\"startovertitle\":\"Start Over\",\"continue\":\"✅\",\"submitanswer\":\"🆗\",\"submitanswertitle\":\"Submit Answer\",\"previoustopic\":\"⬅\",\"nexttopic\":\"➡\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"🔁\"},\"text\":{\"startover\":\"⏮\",\"areyousure\":\"🤔\",\"youmustcomplete\":\"⚠️ 👉 🧑‍💻\",\"exercise\":\"\",\"exercise_plural\":\"\",\"inthissection\":\"\",\"code\":\"💻\",\"enginecap\":\"$t(text.code) {{engine}}\",\"oxfordcomma\":\"\"}}},\"eu\":{\"translation\":{\"button\":{\"runcode\":\"Kodea egikaritu\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Laguntza\",\"hint_plural\":\"Laguntza\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Aurreko laguntza\",\"hintprev\":\"Hurrengo laguntza\",\"solution\":\"Ebazpena\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Arbelean kopiatu\",\"startover\":\"Berrabiarazi\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Jarraitu\",\"submitanswer\":\"Erantzuna bidali\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Aurreko atala\",\"nexttopic\":\"Hurrengo atala\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Berriro saiatu\"},\"text\":{\"startover\":\"Berrabiarazi\",\"areyousure\":\"Berriro hasi nahi duzu? (egindako lana galdu egingo da)\",\"youmustcomplete\":\"Aurrera egin baino lehen atal honetako\",\"exercise\":\"ariketa egin behar duzu.\",\"exercise_plural\":\"ariketak egin behar dituzu.\",\"inthissection\":\"\",\"code\":\"Kodea\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Galdetegia\",\"oxfordcomma\":\"\"}}},\"de\":{\"translation\":{\"button\":{\"runcode\":\"Code ausführen\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Tipp\",\"hint_plural\":\"Tipps\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Nächster Tipp\",\"hintprev\":\"Vorheriger Tipp\",\"solution\":\"Lösung\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"In die Zwischenablage kopieren\",\"startover\":\"Neustart\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Weiter\",\"submitanswer\":\"Antwort einreichen\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Vorheriges Kapitel\",\"nexttopic\":\"Nächstes Kapitel\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Nochmal versuchen\"},\"text\":{\"startover\":\"Neustart\",\"areyousure\":\"Bist du sicher, dass du neustarten willst? (der gesamte Lernfortschritt wird gelöscht)\",\"youmustcomplete\":\"Vervollstädinge\",\"exercise\":\"die Übung\",\"exercise_plural\":\"die Übungen\",\"inthissection\":\"in diesem Kapitel, bevor du fortfährst.\",\"code\":\"Code\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Quiz\",\"blank\":\"Lücke\",\"blank_plural\":\"Lücken\",\"pleasereplaceblank\":\"Bitte ersetze {{blank}} mit gültigem Code.\",\"unparsable\":\"Dies scheint kein gültiger R Code zu sein. R kann deinen Text nicht in einen gültigen Befehl übersetzen. Du hast vielleicht vergessen, die Lücke zu füllen, einen Unterstrich zu entfernen, ein Komma zwischen Argumente zu setzen oder ein eröffnendes <code>&quot;<\\/code>, <code>'<\\/code>, <code>(<\\/code> oder <code>{<\\/code> mit einem zugehörigen <code>&quot;<\\/code>, <code>'<\\/code>, <code>)<\\/code> oder <code>}<\\/code> zu schließen.\\n\",\"and\":\"und\",\"or\":\"oder\",\"listcomma\":\", \",\"oxfordcomma\":\",\"}}},\"ko\":{\"translation\":{\"button\":{\"runcode\":\"코드 실행\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"힌트\",\"hint_plural\":\"힌트들\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"다음 힌트\",\"hintprev\":\"이전 힌트\",\"solution\":\"솔루션\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"클립보드에 복사\",\"startover\":\"재학습\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"다음 학습으로\",\"submitanswer\":\"정답 제출\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"이전 토픽\",\"nexttopic\":\"다음 토픽\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"재시도\"},\"text\":{\"startover\":\"재학습\",\"areyousure\":\"다시 시작 하시겠습니까? (모든 예제의 진행 정보가 재설정됩니다)\",\"youmustcomplete\":\"당신은 완료해야 합니다\",\"exercise\":\"연습문제\",\"exercise_plural\":\"연습문제들\",\"inthissection\":\"이 섹션을 실행하기 전에\",\"code\":\"코드\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"퀴즈\",\"blank\":\"공백\",\"blank_plural\":\"공백들\",\"exercisecontainsblank\":\"이 연습문제에는 {{count}}개의 $t(text.blank)이 포함되어 있습니다.\",\"pleasereplaceblank\":\"{{blank}}를 유효한 코드로 바꾸십시오.\",\"unparsable\":\"이것은 유효한 R 코드가 아닐 수 있습니다. R은 텍스트를 완전한 명령으로 변환하는 방법을 결정할 수 없습니다. 당신은 공백이나 밑줄을 대체하여 채우기, 인수를 컴마로 구분하기, 또는 <code>&quot;<\\/code>, <code>'<\\/code>, <code>(<\\/code> , <code>{<\\/code>로 시작하는 구문을 닫는 <code>&quot;<\\/code>, <code>'<\\/code>, <code>)<\\/code>, <code>}<\\/code>을 잊었을 수도 있습니다.\\n\",\"and\":\"그리고\",\"or\":\"혹은\",\"listcomma\":\", \",\"oxfordcomma\":\"\"}}},\"zh\":{\"translation\":{\"button\":{\"runcode\":\"运行代码\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"提示\",\"hint_plural\":\"提示\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"下一个提示\",\"hintprev\":\"上一个提示\",\"solution\":\"答案\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"复制到剪切板\",\"startover\":\"重新开始\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"继续\",\"submitanswer\":\"提交答案\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"上一专题\",\"nexttopic\":\"下一专题\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"再试一次\"},\"text\":{\"startover\":\"重置\",\"areyousure\":\"你确定要重新开始吗? (所有当前进度将被重置)\",\"youmustcomplete\":\"你必须完成\",\"exercise\":\"练习\",\"exercise_plural\":\"练习\",\"inthissection\":\"在进行本节之前\",\"code\":\"代码\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"测试\",\"blank\":\"空\",\"blank_plural\":\"空\",\"exercisecontainsblank\":\"本练习包含{{count}}个$t(text.blank)\",\"pleasereplaceblank\":\"请在{{blank}}内填写恰当的代码\",\"unparsable\":\"这似乎不是有效的R代码。 R不知道如何将您的文本转换为完整的命令。 您是否忘了填空，忘了删除下划线，忘了在参数之间包含逗号，或者是忘了用<code>&quot;<\\/code>, <code>'<\\/code>, <code>)<\\/code>,<code>}<\\/code>来封闭<code>&quot;<\\/code>, <code>'<\\/code>, <code>(<\\/code>。 or <code>{<\\/code>。\\n\",\"unparsablequotes\":\"<p>您的R代码中似乎含有特殊格式的引号，或者弯引号(<code>{{character}}<\\/code>) 在字符串前后，在R中字符串应该被直引号(<code>&quot;<\\/code> 或者 <code>'<\\/code>)包裹。<\\/p> {{code}} <p>别担心，该错误经常在复制粘贴包含格式的代码时遇到， 您可以尝试将该行中的代码替换为以下代码，也许还有其他地方需要修改。<\\/p> {{suggestion}}\\n\",\"unparsableunicode\":\"<p>您的代码中似乎包含有异常字符(<code>{{character}}<\\/code>),导致代码无效。<\\/p> {{code}} <p>有时候你的代码可能含有看似正常字符的特殊字符，特别是当你复制粘贴其他来源代码的时候。 请试着删除这些特殊字符,重新输入<\\/p>\\n\",\"unparsableunicodesuggestion\":\"<p>您的代码中似乎包含有异常字符(<code>{{character}}<\\/code>),导致代码无效。<\\/p> {{code}} <p>有时候你的代码可能含有看似正常字符的特殊字符，特别是当你复制粘贴其他来源代码的时候。 请试着删除这些特殊字符,重新输入<\\/p>\\n\",\"and\":\"且\",\"or\":\"或\",\"listcomma\":\",\",\"oxfordcomma\":\",\"}}},\"pl\":{\"translation\":{\"button\":{\"runcode\":\"Uruchom kod\",\"runcodetitle\":\"$t(button.runcode) ({{kbd}})\",\"hint\":\"Podpowiedź\",\"hint_plural\":\"Podpowiedzi\",\"hinttitle\":\"$t(button.hint)\",\"hintnext\":\"Następna podpowiedź\",\"hintprev\":\"Poprzednia podpowiedź\",\"solution\":\"Rozwiązanie\",\"solutiontitle\":\"$t(button.solution)\",\"copyclipboard\":\"Kopiuj do schowka\",\"startover\":\"Zacznij od początku\",\"startovertitle\":\"$t(button.startover)\",\"continue\":\"Kontynuuj\",\"submitanswer\":\"Wyślij\",\"submitanswertitle\":\"$t(button.submitanswer)\",\"previoustopic\":\"Poprzednia sekcja\",\"nexttopic\":\"Następna sekcja\",\"questionsubmit\":\"$t(button.submitanswer)\",\"questiontryagain\":\"Spróbuj ponownie\"},\"text\":{\"startover\":\"Zacznij od początku\",\"areyousure\":\"Czy na pewno chcesz zacząć od początku? (cały postęp w zadaniu zostanie utracony)\",\"youmustcomplete\":\"Musisz ukończyć\",\"exercise\":\"ćwiczenie\",\"exercise_plural\":\"ćwiczenia\",\"inthissection\":\"w tej sekcji przed kontynuowaniem\",\"code\":\"Kod\",\"enginecap\":\"$t(text.code) {{engine}}\",\"quiz\":\"Quiz\",\"blank\":\"luka\",\"blank_plural\":\"luk(i)\",\"exercisecontainsblank\":\"To ćwiczenie zawiera {{count}} $t(text.blank).\",\"pleasereplaceblank\":\"Proszę uzupełnić {{blank}} prawidłowym kodem.\",\"unparsable\":\"Wygląda na to, że może to nie być prawidłowy kod R. R nie jest w stanie przetworzyć Twojego tekstu na polecenie. Mogłeś(-aś) zapomnieć wypełnić luki, usunąć podkreślnik, umieścić przecinka między argumentami, lub zamknąć znak <code>&quot;<\\/code>, <code>'<\\/code>, <code>(<\\/code> lub <code>{<\\/code> odpowiadającym <code>&quot;<\\/code>, <code>'<\\/code>, <code>)<\\/code> lub <code>}<\\/code>.\\n\",\"unparsablequotes\":\"<p>Wygląda na to, że Twój kod zawiera szczególnie sformatowane cudzysłowy lub cudzysłowy typograficzne (<code>{{character}}<\\/code>) przy ciągach znaków, co sprawia, że kod jest niepoprawny. R wymaga cudzysłowów prostych (<code>&quot;<\\/code> albo <code>'<\\/code>).<\\/p> {{code}} <p>Nie martw się, to powszechne źródło błędów, gdy kopiuje się kod z innego programu, który sam formatuje teskt. Możesz spróbować zastąpić swój kod następującym kodem. Mogą być też inne miejsca, które wymagają poprawienia.<\\/p> {{suggestion}}\\n\",\"unparsableunicode\":\"<p>Wygląda na to, że Twój kod zawiera niespodziewany znak specjalny (<code>{{character}}<\\/code>), co sprawia, że kod jest niepoprawny.<\\/p> {{code}} <p>Czasami Twój kod może zawierać znak specjalny, który wygląda jak zwykły znak, zwłaszcza jeśli kopiujesz kod z innego programu. Spróbuj usunąć znak specjalny i wpisać do ponownie ręcznie.<\\/p>\\n\",\"unparsableunicodesuggestion\":\"<p>Wygląda na to, że Twój kod zawiera niespodziewany znak specjalny (<code>{{character}}<\\/code>), co sprawia, że kod jest niepoprawny.<\\/p> {{code}} <p>Czasami Twój kod może zawierać znak specjalny, który wygląda jak zwykły znak, zwłaszcza jeśli kopiujesz kod z innego programu. Możesz spróbować zastąpić swój kod następującym kodem. Mogą być też inne miejsca, które wymagają poprawienia.<\\/p> {{suggestion}}\\n\",\"and\":\"i\",\"or\":\"lub\",\"listcomma\":\", \",\"oxfordcomma\":\"\"}}}}}<\/script>"]},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["tutorial-format"]},{"type":"character","attributes":{},"value":["0.11.3"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmarkdown/templates/tutorial/resources"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["tutorial-format.js"]},{"type":"character","attributes":{},"value":["tutorial-format.css","rstudio-theme.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["jquery"]},{"type":"character","attributes":{},"value":["3.6.0"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/3.6.0"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["jquery-3.6.0.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["jquerylib"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.1.4"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["navigation"]},{"type":"character","attributes":{},"value":["1.1"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmd/h/navigation-1.1"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["tabsets.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["rmarkdown"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["2.21"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["highlightjs"]},{"type":"character","attributes":{},"value":["9.12.0"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["rmd/h/highlightjs"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["highlight.js"]},{"type":"character","attributes":{},"value":["default.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["rmarkdown"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["2.21"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["jquery"]},{"type":"character","attributes":{},"value":["3.6.0"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/3.6.0"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["jquery-3.6.0.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["jquerylib"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.1.4"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["font-awesome"]},{"type":"character","attributes":{},"value":["6.2.1"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["fontawesome"]}]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["css/all.min.css","css/v4-shims.min.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["fontawesome"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.5.0"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["bootbox"]},{"type":"character","attributes":{},"value":["5.5.2"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/bootbox"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["bootbox.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["idb-keyvalue"]},{"type":"character","attributes":{},"value":["3.2.0"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/idb-keyval"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["idb-keyval-iife-compat.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[false]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["tutorial"]},{"type":"character","attributes":{},"value":["0.11.3"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/tutorial"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["tutorial.js"]},{"type":"character","attributes":{},"value":["tutorial.css"]},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["ace"]},{"type":"character","attributes":{},"value":["1.10.1"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/ace"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["ace.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["clipboardjs"]},{"type":"character","attributes":{},"value":["2.0.10"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/clipboardjs"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["clipboard.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["ace"]},{"type":"character","attributes":{},"value":["1.10.1"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/ace"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["ace.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["name","version","src","meta","script","stylesheet","head","attachment","package","all_files","pkgVersion"]},"class":{"type":"character","attributes":{},"value":["html_dependency"]}},"value":[{"type":"character","attributes":{},"value":["clipboardjs"]},{"type":"character","attributes":{},"value":["2.0.10"]},{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["file"]}},"value":[{"type":"character","attributes":{},"value":["lib/clipboardjs"]}]},{"type":"NULL"},{"type":"character","attributes":{},"value":["clipboard.min.js"]},{"type":"NULL"},{"type":"NULL"},{"type":"NULL"},{"type":"character","attributes":{},"value":["learnr"]},{"type":"logical","attributes":{},"value":[true]},{"type":"character","attributes":{},"value":["0.11.3"]}]}]}
</script>
<!--/html_preserve-->
<!--html_preserve-->
<script type="application/shiny-prerendered" data-context="execution_dependencies">
{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["packages"]}},"value":[{"type":"list","attributes":{"names":{"type":"character","attributes":{},"value":["packages","version"]},"class":{"type":"character","attributes":{},"value":["data.frame"]},"row.names":{"type":"integer","attributes":{},"value":[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67]}},"value":[{"type":"character","attributes":{},"value":["ade4","backports","base","bslib","cachem","checkmate","cli","colorspace","commonmark","compiler","curl","datasets","digest","dplyr","ellipsis","evaluate","factoextra","fansi","fastmap","fontawesome","generics","ggplot2","ggrepel","glue","graphics","grDevices","grid","gtable","htmltools","htmlwidgets","httpuv","jquerylib","jsonlite","knitr","later","learnr","lifecycle","magrittr","markdown","MASS","methods","mime","munsell","pillar","pkgconfig","promises","R6","Rcpp","rlang","rmarkdown","rprojroot","rstudioapi","sass","scales","shiny","stats","tibble","tidyselect","tools","Unidad2EST2","utf8","utils","vctrs","withr","xfun","xtable","yaml"]},{"type":"character","attributes":{},"value":["1.7-22","1.4.1","4.2.3","0.4.2","1.0.7","2.1.0","3.6.0","2.1-0","1.9.0","4.2.3","5.0.0","4.2.3","0.6.31","1.1.1","0.3.2","0.20","1.0.7","1.0.4","1.1.1","0.5.0","0.1.3","3.4.1","0.9.3","1.6.2","4.2.3","4.2.3","4.2.3","0.3.3","0.5.4","1.6.2","1.6.9","0.1.4","1.8.4","1.42","1.3.0","0.11.3","1.0.3","2.0.3","1.5","7.3-58.2","4.2.3","0.12","0.5.0","1.9.0","2.0.3","1.2.0.1","2.5.1","1.0.10","1.1.0","2.21","2.0.3","0.14","0.4.5","1.2.1","1.7.4","4.2.3","3.2.1","1.2.0","4.2.3","0.0.1","1.2.3","4.2.3","0.6.0","2.5.0","0.37","1.8-4","2.3.7"]}]}]}
</script>
<!--/html_preserve-->
