<p align="center">
  <img src="assets/banner.png" alt="_CALCULATOR_ Banner" width="100%">
</p>

# ◈ Web Calculator

[![CI](https://github.com/ISBANDURAHUMAN-R/CODSOFT_taskno_CALCULATOR/actions/workflows/ci.yml/badge.svg)](https://github.com/ISBANDURAHUMAN-R/CODSOFT_taskno_CALCULATOR/actions/workflows/ci.yml)

## ◆ About the Project
Web Calculator is a responsive arithmetic calculator developed using HTML, CSS, and vanilla JavaScript. Created as part of the CodSoft Web Development Internship, it provides clean numerical computation across desktop and mobile screen sizes.

## ❖ Key Features
- Execution of core arithmetic operations (addition, subtraction, multiplication, division).
- Decimal input handling and mathematical expression evaluation.
- Clear screen (AC) and single-character delete functionality.
- Responsive CSS Grid keypad layout with active touch and click feedback.

## ◆ System Architecture
```mermaid
graph TD
    subgraph View ["&nbsp; Responsive CSS Grid UI &nbsp;"]
        Display["&nbsp; LCD Expression &amp; &nbsp;<br/>&nbsp; Result Display &nbsp;"]
        Keypad["&nbsp; CSS Grid Numeric &nbsp;<br/>&nbsp; &amp; Operator Keypad &nbsp;"]
    end

    subgraph Controller ["&nbsp; JavaScript Event Listener Engine &nbsp;"]
        Keypad --> ClickEvent["&nbsp; Click &amp; Touch &nbsp;<br/>&nbsp; Event Handlers &nbsp;"]
        ClickEvent --> ActionRouter{"&nbsp; Token Type? &nbsp;"}
        ActionRouter -- Digit / Dot --> TokenAppend["&nbsp; Append Character &nbsp;<br/>&nbsp; to Expression &nbsp;"]
        ActionRouter -- Operator --> OpAppend["&nbsp; Append Binary &nbsp;<br/>&nbsp; Operator &nbsp;"]
        ActionRouter -- AC --> ClearAll["&nbsp; Reset Display &nbsp;<br/>&nbsp; Buffer &nbsp;"]
        ActionRouter -- DEL --> DelChar["&nbsp; Pop Trailing &nbsp;<br/>&nbsp; Character &nbsp;"]
        ActionRouter -- Equals --> EvalEngine["&nbsp; Expression Evaluation &nbsp;<br/>&nbsp; Engine &nbsp;"]
    end

    subgraph Evaluation ["&nbsp; Evaluation &amp; State Management &nbsp;"]
        TokenAppend --> Buffer["&nbsp; Current Expression &nbsp;<br/>&nbsp; String &nbsp;"]
        OpAppend --> Buffer
        DelChar --> Buffer
        ClearAll --> Buffer
        Buffer --> Display
        EvalEngine --> SafeParse["&nbsp; Safe Math Parser &amp; &nbsp;<br/>&nbsp; DivZero Guard &nbsp;"]
        SafeParse --> OutputState["&nbsp; Format Floating &nbsp;<br/>&nbsp; Result &nbsp;"]
        OutputState --> Display
    end
```

## ⬢ Technologies Used
- HTML5
- CSS3
- JavaScript (ES6)

## § Requirements
- Modern web browser

## ▲ Installation & Execution
```bash
# Open index.html directly or serve locally
python -m http.server 8000
```
Open `http://localhost:8000` in your web browser.

## ※ Developer
Developer: ISBANDU RAHUMAN R  
GitHub: https://github.com/ISBANDURAHUMAN-R
