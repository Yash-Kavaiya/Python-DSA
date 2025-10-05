\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc}
\usepackage{xcolor}
\usepackage{hyperref}
\usepackage{tikz}
\usepackage{listings}
% Remove or comment out any unknown or problematic package lines if errors persist!

% Color theme (Google-like)
\definecolor{GoogleBlue}{RGB}{66,133,244}
\definecolor{GoogleRed}{RGB}{219,68,55}
\definecolor{GoogleYellow}{RGB}{244,160,0}
\definecolor{GoogleGreen}{RGB}{15,157,88}

\usetheme{Madrid}
\setbeamercolor{frametitle}{bg=GoogleBlue, fg=white}
\setbeamercolor{title}{bg=GoogleBlue,fg=white}

% Custom header/footer
\setbeamertemplate{headline}{
  \leavevmode%
  \hbox{%
  \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,left]{palette quaternary}%
    \hspace*{2ex}\textcolor{white}{DSA Interview Notes}
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,right]{palette quaternary}%
    \textcolor{white}{Slide \insertframenumber}\hspace*{2ex}
  \end{beamercolorbox}}%
  \vskip0pt%
}
\setbeamertemplate{footline}{
  \leavevmode%
  \hbox{
  \begin{beamercolorbox}[wd=.33\paperwidth,ht=2.5ex,dp=1ex,left]{palette primary}
    \hspace*{2ex}\href{https://easy-ai-labs.lovable.app/}{\textcolor{white}{Easy AI Labs}}
  \end{beamercolorbox}
  \begin{beamercolorbox}[wd=.34\paperwidth,ht=2.5ex,dp=1ex,center]{palette secondary}
    \href{https://www.linkedin.com/in/yashkavaiya}{\textcolor{white}{Yash Kavaiya}}
  \end{beamercolorbox}
  \begin{beamercolorbox}[wd=.33\paperwidth,ht=2.5ex,dp=1ex,right]{palette tertiary}
    \href{https://www.linkedin.com/company/genai-guru}{\textcolor{white}{Gen AI Guru}}\hspace*{2ex}
  \end{beamercolorbox}
  }
  \vskip0pt%
}

\title{\textbf{DSA Interview Cheat Sheet}}
\subtitle{Time Complexity \& Python Operations}
\author{Easy AI Labs}
\date{\today}

\begin{document}

% Title Slide
\begin{frame}
\titlepage
\end{frame}

% Agenda
\begin{frame}{Agenda}
\begin{itemize}
  \item List, Set, Dict Common Operations in Python
  \item Time Complexity Analysis
  \item Tips to avoid TLE and optimize code
\end{itemize}
\end{frame}

% Table Example
\begin{frame}{Python List Operations - Time Complexity}
\begin{tabular}{lcc}
  Operation        & Average Case & Amortized Worst Case \\
  \hline
  Copy             & $O(n)$ & $O(n)$ \\
  Append           & $O(1)$ & $O(1)$ \\
  Pop last         & $O(1)$ & $O(1)$ \\
  Pop intermediate & $O(n)$ & $O(n)$ \\
  Insert           & $O(n)$ & $O(n)$ \\
  Get/Set Item     & $O(1)$ & $O(1)$ \\
  Delete Item      & $O(n)$ & $O(n)$ \\
  Iteration        & $O(n)$ & $O(n)$ \\
  Get Slice        & $O(k)$ & $O(k)$ \\
  Sort             & $O(n \log n)$ & $O(n \log n)$ \\
  x in s           & $O(n)$ & $O(n)$ \\
  min(s), max(s)   & $O(n)$ & $O(n)$ \\
  len(s)           & $O(1)$ & $O(1)$ \\
\end{tabular}
\end{frame}

% Code Example (use lstlisting for robust code)
\begin{frame}[fragile]{Python Example: Reverse a Number}
\begin{lstlisting}[language=Python]
num = 5873
reverse_num = 0
while num > 0:
    last_digit = num % 10
    reverse_num = reverse_num * 10 + last_digit
    num = num // 10
print(reverse_num)  # Output: 3785
\end{lstlisting}
\end{frame}

% Visual (TikZ)
\begin{frame}{Digit Extraction Step}
\begin{tikzpicture}[scale=1.0]
\node[draw,fill=GoogleYellow!10,rounded corners,minimum width=1.6cm,minimum height=0.9cm] at (0,1.8) {5873};
\draw[->,thick,GoogleBlue] (0,1.3) -- (0,0.8);
\node[draw,fill=GoogleRed!10,rounded corners] at (0,0.2) {5873\%10 = 3};
\draw[->,thick,GoogleBlue] (0,-0.2) -- (0,-0.7);
\node[draw,fill=GoogleBlue!10,rounded corners] at (0,-1.4) {5873 // 10 = 587};
\end{tikzpicture}
\end{frame}

% Key Takeaways
\begin{frame}{Key Takeaways}
\begin{itemize}
    \item Always check operation complexity before use
    \item List insert/delete in the middle is slow
    \item Set/Dict are $O(1)$ for lookup/update (average)
    \item Avoid nested loops for big lists; use $O(n \log n)$ algorithms where possible
\end{itemize}
\textbf{Follow for more:}\\
\url{https://easy-ai-labs.lovable.app/} | \url{https://www.youtube.com/@genai-guru}
\end{frame}
\end{document}
