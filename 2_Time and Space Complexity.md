\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc}
\usepackage{tikz}
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{hyperref}
\usepackage{graphicx}
\usepackage{xcolor}

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
    \hspace*{2ex}\textcolor{white}{Time \& Space Complexity}
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,right]{palette quaternary}%
    \textcolor{white}{Slide \insertframenumber}\hspace*{2ex}
  \end{beamercolorbox}}%
  \vskip0pt%
}

% Title Page Information
\title{\textbf{Time \& Space Complexity}}
\subtitle{Understanding Algorithm Efficiency}
\author{Presented by Expert}
\institute{Data Structures \& Algorithms Fundamentals}
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
\node[fill=GoogleBlue!20,rounded corners,minimum width=10cm,minimum height=2cm] {
\begin{minipage}{9cm}
\centering
\textcolor{GoogleBlue}{\textbf{Master the Art of Analyzing Algorithms}}\\[0.3cm]
\textcolor{GoogleRed}{Learn Big O Notation, Time Complexity \& Space Complexity}\\[0.2cm]
\textcolor{GoogleGreen}{\small Essential for Coding Interviews \& Software Development}
\end{minipage}
};
\end{tikzpicture}
\end{center}
\end{frame}
}

% Agenda Slide
\begin{frame}{Agenda}
\begin{block}{What We'll Cover Today}
\begin{enumerate}
\item \textcolor{GoogleBlue}{\textbf{What is Time Complexity?}}
\begin{itemize}
\item Definition and importance
\item Common misconceptions
\end{itemize}

\item \textcolor{GoogleRed}{\textbf{Why Interviewers Always Ask About Complexity}}
\begin{itemize}
\item Real-world applications
\item Scalability considerations
\end{itemize}

\item \textcolor{GoogleYellow}{\textbf{Different Types of Notations}}
\begin{itemize}
\item Big O, Omega, and Theta
\item Best, Average, and Worst Case
\end{itemize}

\item \textcolor{GoogleGreen}{\textbf{Rules to Calculate Complexity}}
\begin{itemize}
\item Step-by-step methodology
\item Practical examples
\end{itemize}
\end{enumerate}
\end{block}
\end{frame}

% What is Time Complexity
\begin{frame}{What is Time Complexity?}
\begin{block}{Common Misconception}
\textcolor{GoogleRed}{\textbf{WRONG:}} Time complexity = Time taken to run the code (in seconds)
\end{block}

\begin{block}{Correct Definition}
\textcolor{GoogleGreen}{\textbf{Time Complexity}} is the \textbf{rate of increase in time} with respect to input size
\end{block}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Why Not Seconds?}
\begin{itemize}
\item Different machines (MacBook vs old PC)
\item Different processors
\item Server speed varies
\item Not a reliable metric
\end{itemize}

\column{0.5\textwidth}
\textbf{Rate of Growth}
\begin{itemize}
\item MacBook: Fast processing
\item Old PC: Slow processing
\item Both show growth rate
\item Rate matters, not exact time
\end{itemize}
\end{columns}
\end{frame}

% Rate of Increase Explanation
\begin{frame}{Understanding Rate of Increase}
\begin{center}
\textbf{\Large Rate of Increase in Time}\\[0.3cm]
\textcolor{GoogleBlue}{with respect to}\\[0.3cm]
\textbf{\Large Input Size}
\end{center}

\vspace{0.5cm}

\begin{block}{Example}
If you have 500 lines of code that processes data:
\begin{itemize}
\item \textbf{Input Size 500:} Takes certain time
\item \textbf{Input Size 1000:} Takes more time
\item \textbf{Input Size 5000:} Takes even more time
\end{itemize}
\vspace{0.2cm}
The \textcolor{GoogleRed}{\textbf{rate}} at which time increases is what we measure!
\end{block}

\begin{center}
\begin{tikzpicture}
\draw[->,thick,GoogleGreen] (0,0) -- (8,0) node[right] {Input Size};
\draw[->,thick,GoogleGreen] (0,0) -- (0,4) node[above] {Time};
\draw[thick,GoogleBlue,line width=2pt] (0,0) -- (7,3.5);
\node at (4,2.5) [GoogleRed] {\(\theta\) (Rate/Slope)};
\end{tikzpicture}
\end{center}
\end{frame}

% Big O Notation
\begin{frame}[fragile]{Big O Notation}
\begin{block}{What is Big O?}
Big O Notation is used to express time complexity
\end{block}

\begin{center}
\textbf{\Large \textcolor{GoogleBlue}{O(expression)}}
\end{center}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Simple Example:}
\begin{verbatim}
for i in range(1, n+1):
    print("Aniruddh")
\end{verbatim}

\vspace{0.3cm}
\textbf{Operations per loop:}
\begin{itemize}
\item Compare: \( i < n \)
\item Print statement
\item Increment: \( i = i + 1 \)
\end{itemize}

\column{0.5\textwidth}
\textbf{Calculation:}
\begin{itemize}
\item 3 operations per iteration
\item Loop runs \( n \) times
\item Total: \( 3 \times n = 3n \)
\end{itemize}

\vspace{0.5cm}
\begin{center}
\colorbox{GoogleGreen!20}{
\textcolor{GoogleBlue}{\textbf{Time Complexity = O(3n)}}
}
\end{center}

\vspace{0.3cm}
After simplification:\\
\colorbox{GoogleYellow!20}{
\textcolor{GoogleRed}{\textbf{Time Complexity = O(n)}}
}
\end{columns}
\end{frame}

% Why Interviewers Care
\begin{frame}{Why Interviewers Always Ask About Complexity}
\begin{block}{Real-World Scenario}
You built a website. What should you optimize for?
\end{block}

\vspace{0.3cm}

\begin{columns}
\column{0.5\textwidth}
\begin{center}
\textcolor{GoogleRed}{\textbf{Option A}}\\
100 Users
\end{center}

\column{0.5\textwidth}
\begin{center}
\textcolor{GoogleGreen}{\textbf{Option B}}\\
10 Lakh (1 Million) Users
\end{center}
\end{columns}

\vspace{0.5cm}

\begin{block}{The Answer}
\textbf{Always think WORST CASE!}
\begin{itemize}
\item Your website should handle \textcolor{GoogleBlue}{\textbf{maximum traffic}}
\item Server shouldn't crash under load
\item Code should be \textcolor{GoogleGreen}{\textbf{efficient}} for large inputs
\end{itemize}
\end{block}

\begin{alertblock}{Key Insight}
If your code handles the \textcolor{GoogleRed}{\textbf{worst case}} efficiently, it will obviously handle smaller cases well too!
\end{alertblock}
\end{frame}

% Best, Average, Worst Case
\begin{frame}[fragile]{Best, Average, and Worst Case Analysis}
\begin{block}{Example Code}
\begin{verbatim}
if age > 80:
    print("Super Senior")
elif 60 <= age <= 80:
    print("Senior")
elif 24 <= age <= 60:
    print("Working Professional")
elif 16 <= age <= 24:
    print("Student")
else:
    print("Baby")
\end{verbatim}
\end{block}

\begin{columns}
\column{0.33\textwidth}
\begin{block}{Best Case}
\textcolor{GoogleGreen}{\textbf{Age = 90}}\\
Operations: 2\\
(1 check + 1 print)
\end{block}

\column{0.33\textwidth}
\begin{block}{Average Case}
\textcolor{GoogleYellow}{\textbf{Middle}}\\
\( \frac{\text{Best + Worst}}{2} \)
\end{block}

\column{0.33\textwidth}
\begin{block}{Worst Case}
\textcolor{GoogleRed}{\textbf{Age = 10}}\\
Operations: 5\\
(4 checks + 1 print)
\end{block}
\end{columns}
\end{frame}

% Types of Notations
\begin{frame}{Types of Complexity Notations}
\begin{center}
\begin{tikzpicture}[scale=1.1]
% Big O
\node[fill=GoogleRed!30,rounded corners,minimum width=3.5cm,minimum height=1.5cm] at (0,3) {
\begin{minipage}{3cm}
\centering
\textbf{Big O (O)}\\
\textcolor{GoogleRed}{Worst Case}\\
Upper Bound
\end{minipage}
};

% Theta
\node[fill=GoogleYellow!30,rounded corners,minimum width=3.5cm,minimum height=1.5cm] at (5,3) {
\begin{minipage}{3cm}
\centering
\textbf{Theta (\(\Theta\))}\\
\textcolor{GoogleYellow!80!black}{Average Case}\\
Tight Bound
\end{minipage}
};

% Omega
\node[fill=GoogleGreen!30,rounded corners,minimum width=3.5cm,minimum height=1.5cm] at (10,3) {
\begin{minipage}{3cm}
\centering
\textbf{Omega (\(\Omega\))}\\
\textcolor{GoogleGreen}{Best Case}\\
Lower Bound
\end{minipage}
};

% Most Important
\node[fill=GoogleBlue!30,rounded corners,minimum width=11cm,minimum height=1.2cm] at (5,1) {
\begin{minipage}{10cm}
\centering
\textcolor{GoogleBlue}{\textbf{\Large Interviewers ALWAYS ask for Big O (Worst Case)}}\\
\small We will focus on Big O notation throughout this course
\end{minipage}
};
\end{tikzpicture}
\end{center}

\vspace{0.3cm}

\begin{alertblock}{Important Note}
Theta (\(\Theta\)) and Omega (\(\Omega\)) are taught in college but rarely used in interviews.\\
\textbf{Focus on Big O notation!}
\end{alertblock}
\end{frame}

% Three Golden Rules
\begin{frame}{Three Golden Rules to Calculate Time Complexity}
\begin{block}{\textcolor{GoogleRed}{\textbf{Rule 1:}} Always Calculate in Terms of Worst Case}
Always assume the \textbf{maximum input size} and \textbf{worst scenario}
\end{block}

\begin{block}{\textcolor{GoogleYellow}{\textbf{Rule 2:}} Avoid Constant Values}
Remove all constants from the expression\\
Example: \( O(8n + 6 + 3n^2 + 15) \rightarrow O(n^2) \)
\end{block}

\begin{block}{\textcolor{GoogleGreen}{\textbf{Rule 3:}} Avoid Lower Bounds}
Remove lower order terms (keep only the dominant term)\\
Example: \( O(n^2 + n) \rightarrow O(n^2) \)
\end{block}

\begin{center}
\colorbox{GoogleBlue!20}{
\begin{minipage}{0.9\textwidth}
\centering
\textbf{These rules apply to ALL problems!}\\
Master them and you can calculate complexity for any code.
\end{minipage}
}
\end{center}
\end{frame}

% Why Avoid Constants
\begin{frame}{Why Avoid Constants?}
\begin{block}{Example Expression}
\[ O(8n^{10} + 6 + 3n^2 + 15) \]
\end{block}

\begin{columns}
\column{0.5\textwidth}
\textbf{For n = 10:}
\begin{align*}
&8 \times 10^{10} = 8,000,000,000 \\
&3 \times 10^2 = 300 \\
&\text{Constants} = 21
\end{align*}

\vspace{0.3cm}
\textcolor{GoogleRed}{300 and 21 are negligible compared to 8 billion!}

\column{0.5\textwidth}
\textbf{Simplification Steps:}
\begin{enumerate}
\item Remove constants: 15, 6
\item \( O(8n^{10} + 3n^2) \)
\item Remove lower terms: \(3n^2\)
\item \( O(8n^{10}) \)
\item Remove coefficient: 8
\item \textcolor{GoogleGreen}{\( O(n^{10}) \)}
\end{enumerate}
\end{columns}

\vspace{0.5cm}

\begin{alertblock}{Key Point}
We only care about the \textbf{rate}, not exact operations!\\
\( 3n \) and \( n \) both grow \textbf{linearly}, so we write \( O(n) \)
\end{alertblock}
\end{frame}

% Example 1: Nested Loops
\begin{frame}[fragile]{Example 1: Nested Loops (Equal Bounds)}
\begin{block}{Code}
\begin{verbatim}
for i in range(1, n+1):
    for j in range(1, n+1):
        # Some operation
        print("Code")
\end{verbatim}
\end{block}

\begin{columns}
\column{0.5\textwidth}
\textbf{Analysis:}
\begin{itemize}
\item Outer loop: runs \( n \) times
\item Inner loop: runs \( n \) times for each outer iteration
\item Total operations: \( n \times n = n^2 \)
\end{itemize}

\vspace{0.3cm}
\begin{tabular}{|c|c|}
\hline
\textbf{i value} & \textbf{j runs} \\ \hline
1 & n times \\ \hline
2 & n times \\ \hline
3 & n times \\ \hline
... & ... \\ \hline
n & n times \\ \hline
\end{tabular}

\column{0.5\textwidth}
\textbf{Calculation:}
\[ n + n + n + \ldots + n \text{ (n times)} \]
\[ = n \times n = n^2 \]

\vspace{1cm}

\begin{center}
\colorbox{GoogleGreen!30}{
\Large \textcolor{GoogleBlue}{\textbf{O(\(n^2\))}}
}
\end{center}
\end{columns}
\end{frame}

% Example 2: Nested Loops Different Bounds
\begin{frame}[fragile]{Example 2: Nested Loops (Variable Bounds)}
\begin{block}{Code}
\begin{verbatim}
for i in range(1, n+1):
    for j in range(1, i+1):
        # Some operation
        print("Code")
\end{verbatim}
\end{block}

\begin{columns}
\column{0.5\textwidth}
\textbf{Analysis:}
\begin{itemize}
\item When \( i = 1 \): j runs 1 time
\item When \( i = 2 \): j runs 2 times
\item When \( i = 3 \): j runs 3 times
\item When \( i = n \): j runs n times
\end{itemize}

\vspace{0.3cm}
\textbf{Total operations:}
\[ 1 + 2 + 3 + \ldots + n \]

\column{0.5\textwidth}
\textbf{Using Formula:}
\[ \sum_{i=1}^{n} i = \frac{n(n+1)}{2} \]

\vspace{0.3cm}
\textbf{Simplify:}
\[ = \frac{n^2 + n}{2} = \frac{n^2}{2} + \frac{n}{2} \]

\vspace{0.3cm}
Remove constants and lower terms:
\[ O\left(\frac{n^2}{2}\right) = O(n^2) \]

\vspace{0.5cm}
\begin{center}
\colorbox{GoogleYellow!30}{
\Large \textcolor{GoogleRed}{\textbf{O(\(n^2\))}}
}
\end{center}
\end{columns}
\end{frame}

% Common Time Complexities
\begin{frame}{Common Time Complexities}
\begin{center}
\textbf{\Large Complexity Growth Comparison}
\end{center}

\vspace{0.5cm}

\begin{block}{From Best to Worst (Most Efficient to Least)}
\[ O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(n^3) < O(2^n) < O(n!) \]
\end{block}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Good Complexities:}
\begin{itemize}
\item \textcolor{GoogleGreen}{\(O(1)\)} - Constant
\item \textcolor{GoogleGreen}{\(O(\log n)\)} - Logarithmic
\item \textcolor{GoogleBlue}{\(O(n)\)} - Linear
\item \textcolor{GoogleBlue}{\(O(n \log n)\)} - Linearithmic
\end{itemize}

\column{0.5\textwidth}
\textbf{Avoid if Possible:}
\begin{itemize}
\item \textcolor{GoogleYellow}{\(O(n^2)\)} - Quadratic
\item \textcolor{GoogleRed}{\(O(n^3)\)} - Cubic
\item \textcolor{GoogleRed}{\(O(2^n)\)} - Exponential
\item \textcolor{GoogleRed}{\(O(n!)\)} - Factorial
\end{itemize}
\end{columns}
\end{frame}

% Space Complexity Introduction
\begin{frame}{What is Space Complexity?}
\begin{block}{Definition}
Space Complexity measures the \textbf{memory space} required by an algorithm
\end{block}

\vspace{0.3cm}

\begin{center}
\textbf{\Large Space Complexity = Auxiliary Space + Input Space}
\end{center}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\begin{block}{Auxiliary Space}
\textcolor{GoogleBlue}{\textbf{Extra space}} used to solve the problem
\begin{itemize}
\item Temporary variables
\item Data structures (arrays, dictionaries)
\item Recursion stack
\end{itemize}
\end{block}

\column{0.5\textwidth}
\begin{block}{Input Space}
\textcolor{GoogleGreen}{\textbf{Space used}} to store the input
\begin{itemize}
\item Input array/list
\item Input parameters
\item Initial data
\end{itemize}
\end{block}
\end{columns}

\vspace{0.3cm}

\begin{alertblock}{Important Rule}
\textbf{DO NOT modify the input unless explicitly asked!}
\end{alertblock}
\end{frame}

% Space Complexity Example
\begin{frame}[fragile]{Space Complexity: Example}
\begin{block}{Code}
\begin{verbatim}
x = 5
y = 10
z = 15
total = x + y + z
print(total)
\end{verbatim}
\end{block}

\vspace{0.3cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Input Space:}
\begin{itemize}
\item \( x = 5 \)
\item \( y = 10 \)
\item \( z = 15 \)
\end{itemize}
\textcolor{GoogleRed}{3 variables = Input Space}

\column{0.5\textwidth}
\textbf{Auxiliary Space:}
\begin{itemize}
\item \texttt{total} (extra variable)
\end{itemize}
\textcolor{GoogleGreen}{1 variable = Auxiliary Space}
\end{columns}

\vspace{0.5cm}

\begin{center}
\colorbox{GoogleBlue!20}{
\textbf{Space Complexity} = \textcolor{GoogleRed}{Input Space} + \textcolor{GoogleGreen}{Auxiliary Space}
}
\end{center}

\vspace{0.3cm}

\begin{alertblock}{Don't Do This!}
\begin{verbatim}
x = x + y + z  # Modifying input - BAD!
\end{verbatim}
\end{alertblock}
\end{frame}

% Space Complexity with Arrays
\begin{frame}[fragile]{Space Complexity: Arrays}
\begin{block}{Example}
You create an array/list to solve a problem:
\begin{verbatim}
arr = []  # Empty array
# ... filling array with n elements
\end{verbatim}
\end{block}

\vspace{0.5cm}

\begin{columns}
\column{0.5\textwidth}
\textbf{Worst Case:}
\begin{itemize}
\item Array can grow to size \( n \)
\item Each element takes space
\item Total: \( n \) elements
\end{itemize}

\vspace{0.5cm}
\textcolor{GoogleRed}{\textbf{Space Complexity = O(n)}}

\column{0.5\textwidth}
\begin{center}
\textbf{Array Visualization}\\[0.5cm]
\begin{tikzpicture}
\foreach \x in {0,1,2,3,4} {
    \draw[fill=GoogleBlue!30] (\x*0.8,0) rectangle (\x*0.8+0.7,0.7);
    \node at (\x*0.8+0.35,0.35) {\small \x};
}
\draw[fill=GoogleRed!30] (4,0) rectangle (4.7,0.7);
\node at (4.35,0.35) {\small ...};
\draw[fill=GoogleBlue!30] (4.8,0) rectangle (5.5,0.7);
\node at (5.15,0.35) {\small n};
\node at (2.75,-0.8) {Size = n};
\end{tikzpicture}
\end{center}

\vspace{0.5cm}
\colorbox{GoogleYellow!20}{
\textbf{O(n) space}
}
\end{columns}

\vspace{0.5cm}

\begin{block}{Key Insight}
If you use an array of size \( n \), dictionary with \( n \) elements, or any data structure that grows with input, space complexity is \textcolor{GoogleBlue}{\textbf{O(n)}}
\end{block}
\end{frame}

% Summary Table
\begin{frame}{Quick Reference: Time \& Space Complexity}
\begin{center}
\small
\begin{tabular}{|l|c|c|l|}
\hline
\textbf{Operation} & \textbf{Time} & \textbf{Space} & \textbf{Example} \\ \hline
Single operation & O(1) & O(1) & x = 5 \\ \hline
Single loop (n times) & O(n) & O(1) & for i in range(n) \\ \hline
Nested loops (equal) & O(\(n^2\)) & O(1) & for i... for j... \\ \hline
Nested loops (variable) & O(\(n^2\)) & O(1) & for i... for j in range(i) \\ \hline
Three nested loops & O(\(n^3\)) & O(1) & for i... for j... for k... \\ \hline
Binary search & O(log n) & O(1) & Divide and conquer \\ \hline
Using array size n & O(n) & O(n) & arr = [0] * n \\ \hline
Recursion depth n & O(n) & O(n) & Recursive calls \\ \hline
\end{tabular}
\end{center}

\vspace{0.5cm}

\begin{block}{Remember}
\begin{itemize}
\item Time Complexity: How long does it take?
\item Space Complexity: How much memory does it use?
\item Both use Big O notation: \textcolor{GoogleBlue}{\textbf{O(expression)}}
\end{itemize}
\end{block}
\end{frame}

% Key Takeaways
\begin{frame}{Key Takeaways}
\begin{block}{\textcolor{GoogleBlue}{1. Time Complexity}}
\begin{itemize}
\item NOT about seconds - it's about \textbf{rate of growth}
\item Always calculate for \textcolor{GoogleRed}{\textbf{worst case}}
\item Use \textbf{Big O notation}: O(expression)
\end{itemize}
\end{block}

\begin{block}{\textcolor{GoogleRed}{2. Three Golden Rules}}
\begin{enumerate}
\item Always use worst case
\item Remove constant values
\item Remove lower bound terms
\end{enumerate}
\end{block}

\begin{block}{\textcolor{GoogleGreen}{3. Space Complexity}}
\begin{itemize}
\item Space = Auxiliary Space + Input Space
\item Never modify input unless asked
\item Count extra variables and data structures
\end{itemize}
\end{block}
\end{frame}

% Practice Makes Perfect
\begin{frame}{Practice Makes Perfect!}
\begin{center}
\begin{tikzpicture}
\node[fill=GoogleBlue!30,rounded corners,minimum width=11cm,minimum height=2.5cm] {
\begin{minipage}{10cm}
\centering
\Large \textcolor{GoogleBlue}{\textbf{The More Problems You Solve...}}\\[0.3cm]
\large \textcolor{GoogleRed}{The Better You Get at Calculating Complexity!}\\[0.3cm]
\normalsize Don't worry if it seems confusing now.\\
After solving 100-200 problems, it will become \textbf{second nature}.
\end{minipage}
};
\end{tikzpicture}
\end{center}

\vspace{0.5cm}

\begin{block}{Next Steps}
\begin{itemize}
\item We'll calculate time \& space complexity for \textbf{every problem}
\item You'll see patterns emerge
\item It will become automatic with practice
\end{itemize}
\end{block}

\begin{center}
\textcolor{GoogleGreen}{\textbf{\Large Keep Learning, Keep Growing!}}
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
\item \textbf{Topic:} Time \& Space Complexity - Complete Guide
\item \textbf{Coverage:} Big O Notation, Worst Case Analysis, Practical Examples
\item \textbf{Level:} Beginner to Intermediate
\item \textbf{Target:} CS Students, Interview Prep, Software Developers
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
Data Structures | Algorithms | System Design | AI/ML\\
Coding Interviews | Software Development Best Practices
\end{minipage}
}
\end{center}
\end{frame}
}

\end{document}
