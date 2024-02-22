# médialab LaTeX presentation template

This respository contains a Beamer LaTeX template designed for presentations by members of the médialab.

Once you clone / download this repository onto your computer, you can edit the [`main.tex`](main.tex) file and add slides and/or sections to your presentation.

## Title your presentation

At the top of the [`main.tex`](main.tex) file, edit the bibliographic information about your presentation. Update the title, subtitle, date, and author fields. Change the text in `{Firstname Lastname}` to your name.

```latex
%%% Modify the presentation's bibliographic details
\title{Presentation Title}
\subtitle{Subtitle}
\date{DD MM YYYY}
\author[Firstname Lastname]{Firstname Lastname}
\institute[medialab]
{
  médialab\\
  Sciences Po
}
```

## Add logos

Still in the preamble of the [`main.tex`](main.tex) file, you can insert 1 logo of your project's partners.

To do this, add a PNG image file to the folder [img/](img/) and replace the path in `{theme/logos/partner-logo.png}` with a path to the partner's logo.

If you don't want to show a partner logo, change `\setcounter{PartnerLogo}{1}` to `\setcounter{PartnerLogo}{0}`.

```latex
%%% Reset the logo of the Partner group
\def\PartnerLogo{theme/logos/partner-logo.png}
% If you don't have a partner, set the PartnerLogo count to 0
% If you have a partner, set the PartnerLogo count to 1
\setcounter{PartnerLogo}{1}

```

## Add sections

The [`main.tex`](main.tex) file is meant to be minimal and imports most of the presentation's slides from LaTeX files in the [`Sections/`](Sections/) folder. To add the section to the outline, add `\section{Your Section Name}` to the `main.tex` file. Then import the frames from a LaTeX file. In the example given, the first section is titled "Section A" and the LaTeX file that has the section's slides is located at [`Sections/SectionA.tex`](Sections/SectionA.tex). Notice that, when importing files, you don't add the `.tex` extension to the end of the file name.

```latex
\section{Section A}
\input{Sections/SectionA}
```

## Write slides

If you're writing your slides in imported section files, you don't need to add any preamble, `\begin{document}`, etc. All of that is in the `main.tex` file. The imported file simply has the beamer slides you want in that section. From the top of the file, it can simply begin like this:

```latex
\begin{frame}{Description}
    \lipsum[1]
\end{frame}
```

If you want to add subsections, you'll add them to the section file.

```latex
\subsection{Description}

\begin{frame}{Description of Problem}
    \lipsum[1]
\end{frame}
```

## Compiling LaTeX in Visual Studio Code

An easy way to edit and compile LaTeX in a code editor is to use the Visual Studio Code's extension _LaTeX Workshop_ (James-Yu.latex-workshop).

Once installed, Visual Studio code should recognize this template's LaTeX files and, when you have one open, a green right-facing arrow should be available at the top of the window. Click the arrow to compile the code, and click the preview button next to the arrow to open a side panel showing the results written to the PDF file. Alternatively, simply saving an open LaTeX file should automatically recompile the code.
