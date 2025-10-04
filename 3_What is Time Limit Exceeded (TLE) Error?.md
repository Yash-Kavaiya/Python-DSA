\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc}
\usepackage{tikz}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{hyperref}
\usepackage{graphicx}
\usepackage{xcolor}
\usepackage{listings}

% Google Color Theme
\definecolor{GoogleBlue}{RGB}{66, 133, 244}
\definecolor{GoogleRed}{RGB}{219, 68, 55}
\definecolor{GoogleYellow}{RGB}{244, 160, 0}
\definecolor{GoogleGreen}{RGB}{15, 157, 88}

% Theme Settings
\usetheme{Madrid}
\usecolortheme{default}

% Custom Colors
\setbeamercolor{palette primary}{bg=GoogleBlue,fg=white}
\setbeamercolor{palette secondary}{bg=GoogleRed,fg=white}
\setbeamercolor{palette tertiary}{bg=GoogleYellow,fg=white}
\setbeamercolor{palette quaternary}{bg=GoogleGreen,fg=white}
\setbeamercolor{structure}{fg=GoogleBlue}
\setbeamercolor{frametitle}{bg=GoogleBlue,fg=white}
\setbeamercolor{title}{bg=GoogleBlue,fg=white}
\setbeamercolor{block title}{bg=GoogleGreen,fg=white}
\setbeamercolor{block body}{bg=GoogleGreen!10,fg=black}

% Code Listing Style
\lstset{
    basicstyle=\ttfamily\small,
    keywordstyle=\color{GoogleBlue}\bfseries,
    commentstyle=\color{GoogleGreen},
    stringstyle=\color{GoogleRed},
    showstringspaces=false,
    breaklines=true,
    frame=single,
    backgroundcolor=\color{gray!10}
}

% Footer Setup
\setbeamertemplate{footline}{
  \leavevmode%
  \hbox{%
  \begin{beamercolorbox}[wd=.33\paperwidth,ht=2.5ex,dp=1ex,left]{palette primary}%
    \hspace*{2ex}\href{https://easy-ai-labs.lovable.app/}{\textcolor{white}{Easy AI Labs}}
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.34\paperwidth,ht=2.5ex,dp=1ex,center]{palette secondary}%
    \href{https://www.linkedin.com/in/yashkavaiya}{\textcolor{white}{Yash Kavaiya}}
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.33\paperwidth,ht=2.5ex,dp=1ex,right]{palette tertiary}%
    \href{https://www.linkedin.com/company/genai-guru}{\textcolor{white}{Gen AI Guru}}\hspace*{2ex}
  \end{beamercolorbox}}%
  \vskip0pt%
}

% Header with slide number and topic
\setbeamertemplate{headline}{
  \leavevmode%
  \hbox{%
  \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,left]{palette quaternary}%
    \hspace*{2ex}\textcolor{white}{Time Limit Exceeded (TLE) Error}
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,right]{palette quaternary}%
    \textcolor{white}{Slide \insertframenumber}\hspace*{2ex}
  \end{beamercolorbox}}%
  \vskip0pt%
}

% Title Page Information
\title{\textbf{Time Limit Exceeded (TLE) Error}}
\subtitle{Understanding \& Avoiding TLE in Competitive Programming}
\author{Presented by Expert}
\institute{Coding Interview \& Competitive Programming Series}
\date{\today}

\begin{document}

% Title Slide
{
\setbeamertemplate{headline}{}
\setbeamertemplate{footline}{}
\begin{frame}
\titlepage
\vspace{-1cm}
\begin{center}
\begin{tikzpicture}
\node[fill=GoogleRed!20,rounded corners,minimum width=10cm,minimum height=2cm] {
\begin{minipage}{9cm}
\centering
\textcolor{GoogleRed}{\textbf{Master the Art of Optimizing Your Code}}\\[0.3cm]
\textcolor{GoogleBlue}{Understanding TLE \& How to Solve It}\\[0.2cm]
\textcolor{GoogleGreen}{\small Essential for LeetCode, CodeChef, Codeforces \& More}
\end{minipage}
};
\end{tikzpicture}
\end{center}
\end{frame}
}

% What is TLE?
\begin{frame}{What is Time Limit Exceeded (TLE)?}
\begin{block}{Definition}
\textbf{TLE} stands for \textcolor{GoogleRed}{\textbf{Time Limit Exceeded}}
\end{block}

\vspace{0.3cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Common Platforms with TLE:}
\begin{itemize}
\item LeetCode
\item CodeChef
\item Codeforces
\item GeeksforGeeks
\item HackerRank
\item SPOJ
\end{itemize}

\column{0.5\textwidth}
\begin{alertblock}{What It Means}
Your code is \textcolor{GoogleRed}{\textbf{taking too long}} to execute and doesn't finish within the time limit!
\end{alertblock}

\vspace{0.3cm}
\begin{block}{Important Note}
\textcolor{GoogleGreen}{\textbf{Your logic may be correct!}}\\
TLE doesn't mean wrong answer.\\
It means inefficient approach.
\end{block}
\end{columns}
\end{frame}

% How Code Submission Works
\begin{frame}{How Code Submission Works}
\begin{center}
\begin{tikzpicture}[scale=1.2]
% Code Box
\node[draw,thick,fill=GoogleBlue!20,rounded corners,minimum width=2.5cm,minimum height=1.5cm] (code) at (0,0) {
\textbf{Your Code}
};

% Arrow
\draw[->,ultra thick,GoogleBlue] (code.east) -- (4,0);

% Server Box
\node[draw,thick,fill=GoogleRed!20,rounded corners,minimum width=3cm,minimum height=1.8cm] (server) at (7,0) {
\begin{minipage}{2.5cm}
\centering
\textbf{Server}\\
\small Executes Code\\
Checks Time
\end{minipage}
};

% Time Limit Label
\node[fill=GoogleYellow!30,rounded corners] at (3.5,-1.5) {
\textbf{Time Limit} \(\rightarrow\) 1 sec
};

% Constraints Label
\node[fill=GoogleGreen!30,rounded corners] at (3.5,-2.5) {
\textbf{Constraints}
};

\end{tikzpicture}
\end{center}

\vspace{0.5cm}

\begin{block}{Key Points}
\begin{itemize}
\item Every problem has a \textbf{Time Limit} (usually 1-2 seconds)
\item Every problem has \textbf{Constraints} on input size
\item Server runs your code and checks if it finishes in time
\end{itemize}
\end{block}
\end{frame}

% What Does 1 Second Mean?
\begin{frame}{What Does "1 Second Time Limit" Actually Mean?}
\begin{alertblock}{Common Misconception}
\textcolor{GoogleRed}{\textbf{WRONG:}} Server uses a stopwatch to measure 1 second
\end{alertblock}

\begin{block}{Correct Understanding}
\textcolor{GoogleGreen}{\textbf{1 Second = \(10^8\) Operations (Approximately)}}
\end{block}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{What counts as an operation?}
\begin{itemize}
\item if/else statement
\item Print statement
\item Loop iteration
\item Comparison (\textless, \textgreater, ==)
\item Arithmetic (+, -, *, /)
\end{itemize}

\column{0.5\textwidth}
\begin{center}
\colorbox{GoogleBlue!20}{
\begin{minipage}{4cm}
\centering
\textbf{Rule of Thumb}\\[0.2cm]
\large \(\mathbf{10^8}\) operations\\
\(\approx\) \textbf{1 second}
\end{minipage}
}
\end{center}

\vspace{0.5cm}
\textcolor{GoogleRed}{If operations exceed \(10^8\),\\you'll get TLE!}
\end{columns}
\end{frame}

% Operations Calculation Example
\begin{frame}[fragile]{Understanding Operations}
\begin{block}{Example: Simple Loop}
\begin{lstlisting}[language=Python]
for i in range(1, n+1):
    if i % 2 == 0:
        print(i)
\end{lstlisting}
\end{block}

\begin{columns}
\column{0.5\textwidth}
\textbf{Operations per iteration:}
\begin{enumerate}
\item Loop comparison
\item Modulo operation
\item if condition check
\item Print (if true)
\end{enumerate}

\(\approx\) 3-4 operations per iteration

\column{0.5\textwidth}
\textbf{Total Operations:}
\begin{itemize}
\item Loop runs \(n\) times
\item Each iteration: 3-4 ops
\item Total: \(3n\) to \(4n\) operations
\end{itemize}

\vspace{0.3cm}
\colorbox{GoogleGreen!20}{
\textbf{Time Complexity: O(n)}
}
\end{columns}

\vspace{0.5cm}

\begin{alertblock}{Key Point}
Server counts total operations, not wall-clock time!
\end{alertblock}
\end{frame}

% When Does TLE Occur?
\begin{frame}{When Does TLE Occur?}
\begin{block}{TLE Condition}
TLE occurs when: \textcolor{GoogleRed}{\textbf{Total Operations \textgreater \(10^8\)}}
\end{block}

\vspace{0.5cm}

\begin{center}
\begin{tikzpicture}
% Safe Zone
\draw[fill=GoogleGreen!20,draw=GoogleGreen,thick] (0,0) rectangle (5,1.5);
\node at (2.5,0.75) {\textbf{Safe Zone: \(\leq 10^8\) operations}};

% Danger Zone
\draw[fill=GoogleRed!20,draw=GoogleRed,thick] (6,0) rectangle (11,1.5);
\node at (8.5,0.75) {\textbf{TLE Zone: \textgreater \(10^8\) operations}};

% Examples Below
\node[fill=GoogleGreen!30,rounded corners] at (2.5,-1) {
\begin{minipage}{4cm}
\centering
\small \textbf{Accepted}\\
\(n = 10^6\), O(n)\\
Operations = \(10^6\)
\end{minipage}
};

\node[fill=GoogleRed!30,rounded corners] at (8.5,-1) {
\begin{minipage}{4cm}
\centering
\small \textbf{TLE}\\
\(n = 10^5\), O(\(n^2\))\\
Operations = \(10^{10}\)
\end{minipage}
};
\end{tikzpicture}
\end{center}

\vspace{0.5cm}

\begin{alertblock}{Remember}
Even if \(10^9\) or \(10^{10}\) operations, you'll get TLE!\\
Must stay within \(10^8\) limit.
\end{alertblock}
\end{frame}

% Real Example - Sorting Problem
\begin{frame}[fragile]{Real Example: Sorting Problem}
\begin{block}{Problem Statement}
Given a list, sort it and return.\\
\textbf{Input:} list = [5, 8, 7, 6, 5, 1, 3]
\end{block}

\begin{columns}
\column{0.5\textwidth}
\textbf{Time Limit:} 1 second\\
\textbf{Constraints:}
\begin{itemize}
\item \(1 \leq \text{list\_size} \leq 10^5\)
\end{itemize}

\vspace{0.5cm}
\textbf{Your Solution:}
\begin{itemize}
\item Time Complexity: O(\(n^2\))
\item Using Bubble Sort
\end{itemize}

\column{0.5\textwidth}
\textbf{Worst Case Calculation:}
\begin{itemize}
\item \(n = 10^5\) (maximum)
\item Complexity: O(\(n^2\))
\item Operations: \((10^5)^2 = 10^{10}\)
\end{itemize}

\vspace{0.3cm}
\colorbox{GoogleRed!30}{
\begin{minipage}{4cm}
\centering
\textbf{Will you get TLE?}\\
\textcolor{GoogleRed}{\textbf{YES!}}\\
\(10^{10} \gg 10^8\)
\end{minipage}
}
\end{columns}

\vspace{0.5cm}

\begin{alertblock}{Solution}
Use efficient sorting: O(\(n \log n\))\\
Merge Sort, Quick Sort, or built-in sort()
\end{alertblock}
\end{frame}

% Calculating Operations from Time
\begin{frame}{How Many Seconds Will Your Code Take?}
\begin{block}{Formula}
\textbf{Time (seconds)} = \(\frac{\text{Total Operations}}{10^8}\)
\end{block}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Example from Earlier:}
\begin{itemize}
\item \(n = 10^5\)
\item Complexity: O(\(n^2\))
\item Operations = \(10^{10}\)
\end{itemize}

\vspace{0.3cm}
\textbf{Calculate time:}
\[
\frac{10^{10}}{10^8} = 10^2 = 100 \text{ seconds}
\]

\column{0.5\textwidth}
\begin{center}
\begin{tikzpicture}
\node[fill=GoogleRed!30,rounded corners,minimum width=4.5cm,minimum height=3cm] {
\begin{minipage}{4cm}
\centering
\textbf{Your code will take}\\[0.3cm]
\Huge \textcolor{GoogleRed}{\textbf{100 sec}}\\[0.3cm]
\normalsize But time limit is\\
\Large \textbf{1 sec}\\[0.3cm]
\large \textcolor{GoogleRed}{\textbf{TLE!}}
\end{minipage}
};
\end{tikzpicture}
\end{center}
\end{columns}

\vspace{0.5cm}

\begin{alertblock}{Key Insight}
Your code is correct but \textcolor{GoogleRed}{\textbf{too slow}}!\\
Need to optimize the algorithm.
\end{alertblock}
\end{frame}

% Operations Reference Table
\begin{frame}{Operations Per Second Reference}
\begin{center}
\textbf{\Large Quick Reference Table}
\end{center}

\vspace{0.3cm}

\begin{center}
\small
\begin{tabular}{|c|c|c|}
\hline
\textbf{Operations} & \textbf{Time (approx)} & \textbf{Result} \\ \hline
\(10^6\) & 0.01 sec & \textcolor{GoogleGreen}{\textbf{Safe}} \\ \hline
\(10^7\) & 0.1 sec & \textcolor{GoogleGreen}{\textbf{Safe}} \\ \hline
\(10^8\) & 1 sec & \textcolor{GoogleYellow!80!black}{\textbf{Border}} \\ \hline
\(10^9\) & 10 sec & \textcolor{GoogleRed}{\textbf{TLE}} \\ \hline
\(10^{10}\) & 100 sec & \textcolor{GoogleRed}{\textbf{TLE}} \\ \hline
\(10^{11}\) & 1000 sec & \textcolor{GoogleRed}{\textbf{TLE}} \\ \hline
\end{tabular}
\end{center}

\vspace{0.5cm}

\begin{block}{Golden Rule}
\textbf{Always aim for \(\leq 10^8\) operations!}
\end{block}

\begin{alertblock}{Note}
These are approximate values. Different platforms may vary slightly,\\
but \(10^8\) is a safe universal benchmark.
\end{alertblock}
\end{frame}

% Complexity vs Constraints
\begin{frame}{Matching Complexity with Constraints}
\begin{center}
\textbf{\Large Acceptable Time Complexities}
\end{center}

\vspace{0.3cm}

\begin{center}
\small
\begin{tabular}{|c|c|c|}
\hline
\textbf{Constraint (n)} & \textbf{Acceptable Complexity} & \textbf{Operations} \\ \hline
\(n \leq 10\) & O(\(n!\)), O(\(2^n\)) & Any \\ \hline
\(n \leq 20\) & O(\(2^n\)) & \(\sim 10^6\) \\ \hline
\(n \leq 100\) & O(\(n^4\)) & \(\sim 10^8\) \\ \hline
\(n \leq 500\) & O(\(n^3\)) & \(\sim 10^8\) \\ \hline
\(n \leq 10^4\) & O(\(n^2\)) & \(\sim 10^8\) \\ \hline
\(n \leq 10^5\) & O(\(n \log n\)) & \(\sim 10^6\) \\ \hline
\(n \leq 10^6\) & O(\(n\)) & \(\sim 10^6\) \\ \hline
\(n \leq 10^7\) & O(\(n\)) & \(\sim 10^7\) \\ \hline
\(n \leq 10^8\) & O(\(n\)) & \(\sim 10^8\) \\ \hline
\(n \leq 10^9\) & O(\(\log n\)), O(1) & \(\sim 30\) \\ \hline
\end{tabular}
\end{center}

\vspace{0.3cm}

\begin{alertblock}{How to Use This Table}
1. Check the constraint (maximum value of \(n\))\\
2. Choose complexity that keeps operations \(\leq 10^8\)\\
3. Implement algorithm with that complexity
\end{alertblock}
\end{frame}

% Example Analysis
\begin{frame}{Example: Constraint Analysis}
\begin{block}{Problem Constraint}
\textbf{Given:} \(1 \leq n \leq 10^5\)
\end{block}

\vspace{0.3cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Acceptable:}
\begin{itemize}
\item[\textcolor{GoogleGreen}{\checkmark}] O(1) - Constant
\item[\textcolor{GoogleGreen}{\checkmark}] O(\(\log n\)) - \(\sim 17\)
\item[\textcolor{GoogleGreen}{\checkmark}] O(\(n\)) - \(10^5\)
\item[\textcolor{GoogleGreen}{\checkmark}] O(\(n \log n\)) - \(\sim 10^6\)
\end{itemize}

\column{0.5\textwidth}
\textbf{NOT Acceptable:}
\begin{itemize}
\item[\textcolor{GoogleRed}{\texttimes}] O(\(n^2\)) - \(10^{10}\)
\item[\textcolor{GoogleRed}{\texttimes}] O(\(n^3\)) - \(10^{15}\)
\item[\textcolor{GoogleRed}{\texttimes}] O(\(2^n\)) - Huge
\item[\textcolor{GoogleRed}{\texttimes}] O(\(n!\)) - Huge
\end{itemize}
\end{columns}

\vspace{0.5cm}

\begin{block}{Calculation for O(\(n \log n\))}
\begin{align*}
n \log n &= 10^5 \times \log_2(10^5) \\
&\approx 10^5 \times 17 \\
&\approx 1.7 \times 10^6 \text{ operations} \\
&< 10^8 \quad \textcolor{GoogleGreen}{\checkmark}
\end{align*}
\end{block}
\end{frame}

% Visual Diagram - Sorting Example
\begin{frame}{Visual Example: Why O(\(n^2\)) Gets TLE}
\begin{center}
\begin{tikzpicture}[scale=0.9]
% Problem box
\node[fill=GoogleBlue!20,rounded corners,minimum width=8cm,minimum height=1cm] at (0,4) {
\textbf{Problem:} Sort array where \(1 \leq n \leq 10^5\)
};

% O(n^2) path
\node[fill=GoogleRed!20,rounded corners,minimum width=3.5cm,minimum height=2cm] at (-3,1.5) {
\begin{minipage}{3cm}
\centering
\textbf{O(\(n^2\)) Solution}\\
Bubble Sort\\[0.2cm]
\(n = 10^5\)\\
Operations = \((10^5)^2\)\\
= \(10^{10}\)
\end{minipage}
};

% Arrow to TLE
\draw[->,ultra thick,GoogleRed] (-3,0.5) -- (-3,-0.5);
\node[fill=GoogleRed!30,rounded corners] at (-3,-1.5) {
\textbf{TLE!}\\
100 seconds
};

% O(n log n) path
\node[fill=GoogleGreen!20,rounded corners,minimum width=3.5cm,minimum height=2cm] at (3,1.5) {
\begin{minipage}{3cm}
\centering
\textbf{O(\(n \log n\))}\\
Merge Sort\\[0.2cm]
\(n = 10^5\)\\
Operations \(\approx 10^6\)
\end{minipage}
};

% Arrow to Accepted
\draw[->,ultra thick,GoogleGreen] (3,0.5) -- (3,-0.5);
\node[fill=GoogleGreen!30,rounded corners] at (3,-1.5) {
\textbf{Accepted!}\\
0.01 seconds
};

\end{tikzpicture}
\end{center}

\vspace{0.3cm}

\begin{alertblock}{Key Takeaway}
Same problem, different approach!\\
Algorithm choice determines if you get TLE or Accepted.
\end{alertblock}
\end{frame}

% How to Avoid TLE
\begin{frame}{How to Avoid TLE?}
\begin{block}{\textcolor{GoogleBlue}{Step 1: Read Constraints Carefully}}
Always check maximum value of \(n\) in constraints
\end{block}

\begin{block}{\textcolor{GoogleRed}{Step 2: Calculate Required Complexity}}
Use reference table to determine acceptable complexity
\end{block}

\begin{block}{\textcolor{GoogleYellow}{Step 3: Choose Right Algorithm}}
\begin{itemize}
\item Sorting: O(\(n \log n\)) instead of O(\(n^2\))
\item Searching: Binary Search O(\(\log n\)) vs Linear O(\(n\))
\item Use efficient data structures (HashMap, Set, etc.)
\end{itemize}
\end{block}

\begin{block}{\textcolor{GoogleGreen}{Step 4: Optimize Your Code}}
\begin{itemize}
\item Avoid nested loops when possible
\item Use built-in functions (often optimized)
\item Remove unnecessary operations
\end{itemize}
\end{block}
\end{frame}

% Common TLE Causes
\begin{frame}{Common Causes of TLE}
\begin{columns}
\column{0.5\textwidth}
\textbf{Algorithm Issues:}
\begin{enumerate}
\item Using \textcolor{GoogleRed}{O(\(n^2\))} when O(\(n\)) needed
\item Nested loops unnecessarily
\item Recursive calls without memoization
\item Inefficient sorting/searching
\end{enumerate}

\vspace{0.5cm}
\textbf{Input/Output Issues:}
\begin{enumerate}
\item Slow I/O methods
\item Reading input inefficiently
\item Printing too frequently
\end{enumerate}

\column{0.5\textwidth}
\textbf{Data Structure Issues:}
\begin{enumerate}
\item Using List instead of Set
\item Not using HashMap for lookups
\item Inefficient data access
\item Repeated calculations
\end{enumerate}

\vspace{0.5cm}
\textbf{Code Issues:}
\begin{enumerate}
\item Hidden loops in functions
\item String concatenation in loops
\item Unnecessary type conversions
\item Redundant operations
\end{enumerate}
\end{columns}

\vspace{0.5cm}

\begin{alertblock}{Pro Tip}
Before submitting, calculate: \textbf{Complexity × Max Input \(\leq 10^8\)?}
\end{alertblock}
\end{frame}

% Optimization Techniques
\begin{frame}[fragile]{Quick Optimization Techniques}
\begin{block}{1. Use Efficient Data Structures}
\begin{lstlisting}[language=Python]
# Bad: O(n) lookup
if x in list:  # Searches entire list

# Good: O(1) lookup  
if x in set_collection:  # Instant lookup
\end{lstlisting}
\end{block}

\begin{block}{2. Avoid Nested Loops}
\begin{lstlisting}[language=Python]
# Bad: O(n^2)
for i in range(n):
    for j in range(n):
        # do something

# Good: Use HashMap - O(n)
for i in range(n):
    # use dictionary for O(1) lookup
\end{lstlisting}
\end{block}

\begin{block}{3. Use Built-in Functions}
Built-in sort(), min(), max() are highly optimized in most languages
\end{block}
\end{frame}

% Decision Tree
\begin{frame}{TLE Decision Tree}
\begin{center}
\begin{tikzpicture}[scale=0.85]
% Root
\node[fill=GoogleBlue!30,rounded corners,minimum width=5cm] (start) at (0,5) {
\textbf{Got TLE?}
};

% Check Complexity
\node[fill=GoogleYellow!30,rounded corners,minimum width=4cm] (complex) at (0,3) {
Check Time Complexity
};
\draw[->,thick] (start) -- (complex);

% High Complexity
\node[fill=GoogleRed!20,rounded corners,minimum width=3cm] (high) at (-3,1) {
Too High?\\
O(\(n^2\)), O(\(n^3\))
};
\draw[->,thick] (complex) -- (high);

% Low Complexity
\node[fill=GoogleGreen!20,rounded corners,minimum width=3cm] (low) at (3,1) {
Already Optimal?\\
O(\(n\)), O(\(n \log n\))
};
\draw[->,thick] (complex) -- (low);

% Solutions
\node[fill=GoogleGreen!30,rounded corners] (sol1) at (-3,-0.8) {
\textbf{Optimize Algorithm}
};
\draw[->,thick] (high) -- (sol1);

\node[fill=GoogleBlue!30,rounded corners,minimum width=3cm] (sol2) at (3,-0.8) {
\textbf{Optimize Code}\\
I/O, Data Structures
};
\draw[->,thick] (low) -- (sol2);

\end{tikzpicture}
\end{center}

\vspace{0.3cm}

\begin{block}{Remember}
First fix algorithm complexity, then optimize code details!
\end{block}
\end{frame}

% Python List Operations
\begin{frame}{Common List Operations \& Their Complexity}
\begin{block}{Important for Next Lecture}
We'll study time complexity of list operations in detail
\end{block}

\vspace{0.3cm}

\begin{center}
\small
\begin{tabular}{|l|c|l|}
\hline
\textbf{Operation} & \textbf{Time Complexity} & \textbf{Example} \\ \hline
append() & O(1) & list.append(5) \\ \hline
pop() (end) & O(1) & list.pop() \\ \hline
pop(index) & O(n) & list.pop(0) \\ \hline
insert() & O(n) & list.insert(0, 5) \\ \hline
delete & O(n) & del list[0] \\ \hline
lookup by index & O(1) & x = list[5] \\ \hline
search (in) & O(n) & if 5 in list \\ \hline
\end{tabular}
\end{center}

\vspace{0.5cm}

\begin{alertblock}{Coming Up Next}
Detailed analysis of data structure operations and their impact on TLE!
\end{alertblock}
\end{frame}

% Key Takeaways
\begin{frame}{Key Takeaways}
\begin{block}{\textcolor{GoogleBlue}{1. What is TLE?}}
Time Limit Exceeded = Your code takes too long\\
Not wrong logic, just inefficient approach
\end{block}

\begin{block}{\textcolor{GoogleRed}{2. The \(10^8\) Rule}}
\begin{itemize}
\item 1 second \(\approx 10^8\) operations
\item Keep total operations \(\leq 10^8\)
\item Calculate: Complexity × Max Input Size
\end{itemize}
\end{block}

\begin{block}{\textcolor{GoogleGreen}{3. How to Avoid TLE}}
\begin{itemize}
\item Read constraints carefully
\item Choose appropriate complexity
\item Use efficient algorithms \& data structures
\item Optimize code when needed
\end{itemize}
\end{block}
\end{frame}

% Practice Problems
\begin{frame}{Practice Makes Perfect}
\begin{center}
\begin{tikzpicture}
\node[fill=GoogleBlue!30,rounded corners,minimum width=11cm,minimum height=2.5cm] {
\begin{minipage}{10cm}
\centering
\Large \textcolor{GoogleBlue}{\textbf{Before Submitting Any Code...}}\\[0.3cm]
\large \textcolor{GoogleRed}{Always Calculate:}\\[0.2cm]
\normalsize \textbf{Complexity × Maximum Input Size \(\leq 10^8\)?}\\[0.3cm]
If YES \(\rightarrow\) Submit!\\
If NO \(\rightarrow\) Optimize!
\end{minipage}
};
\end{tikzpicture}
\end{center}

\vspace{0.5cm}

\begin{block}{Next Steps}
\begin{itemize}
\item Practice identifying constraints
\item Learn to estimate operations quickly
\item Study efficient algorithms for common problems
\item Understand data structure complexities
\end{itemize}
\end{block}

\begin{center}
\textcolor{GoogleGreen}{\textbf{\Large Happy Coding! No More TLE! 🚀}}
\end{center}
\end{frame}

% Content Details - Last Slide
{
\setbeamertemplate{headline}{}
\begin{frame}[fragile]{Content Details \& Follow for More Updates}
\begin{center}
\textbf{\LARGE Thank You!}
\end{center}

\vspace{0.3cm}

\begin{block}{Presentation Content}
\begin{itemize}
\item \textbf{Topic:} Time Limit Exceeded (TLE) Error - Complete Guide
\item \textbf{Coverage:} TLE Understanding, \(10^8\) Rule, Optimization Strategies
\item \textbf{Level:} Beginner to Intermediate
\item \textbf{Target:} Competitive Programming, LeetCode, Interview Prep
\end{itemize}
\end{block}

\vspace{0.3cm}

\begin{block}{Connect With Us}
\centering
\begin{tabular}{ll}
\textcolor{GoogleBlue}{\textbf{Website:}} & \href{https://easy-ai-labs.lovable.app/}{easy-ai-labs.lovable.app} \\[0.2cm]
\textcolor{GoogleRed}{\textbf{LinkedIn:}} & \href{https://www.linkedin.com/in/yashkavaiya}{Yash Kavaiya} \\[0.2cm]
\textcolor{GoogleGreen}{\textbf{Company:}} & \href{https://www.linkedin.com/company/genai-guru}{Gen AI Guru} \\[0.2cm]
\textcolor{GoogleYellow!80!black}{\textbf{YouTube:}} & \href{https://www.youtube.com/@genai-guru}{@genai-guru} \\
\end{tabular}
\end{block}

\vspace{0.3cm}

\begin{center}
\colorbox{GoogleBlue!20}{
\begin{minipage}{10cm}
\centering
\textbf{Follow for more updates on:}\\
Competitive Programming | LeetCode Solutions | DSA\\
Time Complexity | Coding Interviews | Algorithm Optimization
\end{minipage}
}
\end{center}
\end{frame}
}

\end{document}
