\documentclass[aspectratio=169]{beamer}
\usepackage[utf8]{inputenc}
\usepackage{hyperref}
\usepackage{xcolor}
\usepackage{tikz}
\usepackage{amsmath}
\usepackage{listings}

% Google color palette
\definecolor{GoogleBlue}{RGB}{66,133,244}
\definecolor{GoogleRed}{RGB}{219,68,55}
\definecolor{GoogleYellow}{RGB}{244,160,0}
\definecolor{GoogleGreen}{RGB}{15,157,88}

\usetheme{Madrid}
\setbeamercolor{frametitle}{bg=GoogleBlue, fg=white}
\setbeamercolor{title}{bg=GoogleBlue,fg=white}

% Header/Footer Style
\setbeamertemplate{headline}{
  \leavevmode%
  \hbox{
    \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,left]{palette quaternary}
      \hspace*{2ex}\textcolor{white}{Python DSA - Check Palindrome}
    \end{beamercolorbox}
    \begin{beamercolorbox}[wd=.5\paperwidth,ht=2.5ex,dp=1ex,right]{palette quaternary}
      \textcolor{white}{Slide \insertframenumber}\hspace*{2ex}
    \end{beamercolorbox}
  }
  \vskip0pt
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
  \vskip0pt
}

\title{Check Palindrome Number}
\subtitle{Python DSA Interview Pattern}
\author{Easy AI Labs}
\date{\today}

\begin{document}

\begin{frame}
    \titlepage
\end{frame}

\begin{frame}{Problem Statement}
\textbf{Input:} An integer $n$ \\
\textbf{Task:} Return True if $n$ is a palindrome, else False

\textbf{What is a Palindrome?}
\begin{itemize}
    \item Reads same forwards and backwards: e.g., $121, 9889, 99, 7$
    \item $1234$: Not a palindrome \\
    \item $1221$: Yes, palindrome
\end{itemize}
\end{frame}

\begin{frame}{Algorithm Idea (No String)} 
\begin{block}{Step-by-step logic}
\begin{itemize}
    \item Let $n=1234$. Store $num = n$, $result = 0$
    \item While $num > 0$:
      \begin{itemize}
        \item $ld = num \% 10$ (last digit)
        \item $result = (result \times 10) + ld$
        \item $num = num // 10$
      \end{itemize}
    \item Finally, check if $result == n$
\end{itemize}
\end{block}

\begin{center}
\begin{tikzpicture}[scale=1.05]
% Steps
\node[draw,fill=GoogleYellow!10,rounded corners] (s1) {num=1234, result=0};
\node[draw,fill=GoogleRed!10,rounded corners,below=of s1] (s2) {num=123, result=4};
\node[draw,fill=GoogleGreen!10,rounded corners,below=of s2] (s3) {num=12, result=43};
\node[draw,fill=GoogleBlue!10,rounded corners,below=of s3] (s4) {num=1, result=432};
\node[draw,rounded corners,below=of s4] (s5) {num=0, result=4321};
\draw[->,thick] (s1) -- (s2);
\draw[->,thick] (s2) -- (s3);
\draw[->,thick] (s3) -- (s4);
\draw[->,thick] (s4) -- (s5);
\end{tikzpicture}
\end{center}
\end{frame}

\begin{frame}[fragile]{Python Code - Palindrome Check (No String)}
\begin{lstlisting}[language=Python]
def is_palindrome(n):
    num = n
    result = 0
    while num > 0:
        ld = num % 10
        result = (result * 10) + ld
        num = num // 10
    return n == result

print(is_palindrome(1234))   # False
print(is_palindrome(1221))   # True
print(is_palindrome(12321))  # True
\end{lstlisting}
\end{frame}

\begin{frame}{Complexity Analysis}
\begin{itemize}
    \item \textbf{Time Complexity:} $O(\log_{10} n)$
    \item \textbf{Space Complexity:} $O(1)$ (two variables: num, result)
\end{itemize}
\end{frame}

\begin{frame}{Best Practices}
\begin{itemize}
    \item Do NOT convert number to string; use arithmetic only
    \item Works for all bases, not just decimal
    \item Handles large numbers efficiently
\end{itemize}
\end{frame}

\begin{frame}{Content Details \& Follow for More}
\begin{block}{Connect With Us}
\begin{tabular}{ll}
\textcolor{GoogleBlue}{\textbf{Website:}} & \href{https://easy-ai-labs.lovable.app/}{easy-ai-labs.lovable.app} \\
\textcolor{GoogleRed}{\textbf{LinkedIn:}} & \href{https://www.linkedin.com/in/yashkavaiya}{Yash Kavaiya} \\
\textcolor{GoogleGreen}{\textbf{Company:}} & \href{https://www.linkedin.com/company/genai-guru}{Gen AI Guru} \\
\textcolor{GoogleYellow!80!black}{\textbf{YouTube:}} & \href{https://www.youtube.com/@genai-guru}{@genai-guru} \\
\end{tabular}
\end{block}
\centering
\colorbox{GoogleBlue!10}{\begin{minipage}{10cm}
\centering
Follow for more DSA and coding interview tips!
\end{minipage}}
\end{frame}

\end{document}
