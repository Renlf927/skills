# LaTeX Layout Reference

Load this file only when the report needs new figure helpers, paired oscilloscope figures, or page-break fixes.

## Figure Helper

```latex
\newcommand{\reportfigure}[4][0.84\textwidth]{%
  \begin{figure}[!htbp]
    \centering
    \includegraphics[width=#1,height=0.44\textheight,keepaspectratio]{#2}
    \caption{#4}
    \label{#3}
  \end{figure}
}
```

## Paired Oscilloscope Helper

```latex
\newcommand{\scopepair}[6]{%
  \begin{figure}[H]
    \centering
    \begin{minipage}{0.48\textwidth}
      \centering
      \includegraphics[width=\linewidth,height=0.20\textheight,keepaspectratio]{#1}\\[-0.2em]
      {\small (a) #2}
    \end{minipage}\hfill
    \begin{minipage}{0.48\textwidth}
      \centering
      \includegraphics[width=\linewidth,height=0.20\textheight,keepaspectratio]{#3}\\[-0.2em]
      {\small (b) #4}
    \end{minipage}
    \caption{#6}
    \label{#5}
  \end{figure}
}
```

## Anti-Bad-Break Pattern

```latex
\begin{samepage}
With \(R_s=1~\mathrm{k}\Omega\), the expected voltage ratio is
\[
\frac{V_i}{V_s}\approx \frac{R_i}{R_i+R_s}.
\]
\end{samepage}
```

## Log Triage

- `Undefined references`: compile again; if still present, fix labels/refs.
- `Overfull \hbox`: shorten table text, reduce `\tabcolsep`, or use narrower wording.
- Large blank area before a figure: reduce figure height or move the figure closer to its first discussion.

