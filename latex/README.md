# LaTeX CV Setup Guide

## Quick Start

### Option 1: Custom Template (Full Control)
The `cv-template.tex` file provides maximum control over formatting with custom commands.

**To compile:**
```bash
cd latex
lualatex cv-template.tex
```

Or with XeLaTeX:
```bash
xelatex cv-template.tex
```

### Option 2: ModernCV (Quick Setup)
The `cv-moderncv.tex` file uses the popular `moderncv` class for a polished look with minimal setup.

**To compile:**
```bash
cd latex
pdflatex cv-moderncv.tex
```

## Required Packages

For the custom template, ensure you have:
- fontspec
- xunicode
- xcolor
- titlesec
- fancyhdr
- geometry
- enumitem
- booktabs
- microtype

Install via (if needed):
```bash
tlmgr install fontspec xunicode xcolor titlesec fancyhdr geometry enumitem booktabs microtype
```

## File Structure

```
cv/
├── latex/
│   ├── cv-template.tex    # Custom professional template
│   ├── cv-moderncv.tex   # Using moderncv class
│   ├── publications.bib   # For bibliography (optional)
│   └── README.md         # This file
├── cv-master             # Source markdown
└── cv-full              # Formatted markdown
```

## Custom Template Commands

The `cv-template.tex` provides these commands:

```latex
% Header
\makeheader

% Section
\cvsection{Section Name}

% Education Entry
\education{degree}{institution}{location}{dates}{details}

% Professional Entry
\professional{title}{institution}{location}{dates}{details}

% Award Entry
\award{name}{details}

% Grant Entry
\grant{name}{amount}{details}

% Course Entry
\course{name}{date}{location}
```

## ModernCV Commands

```latex
% Single item
\cvitem{label}{content}

% Double item (side by side)
\cvlistdoubleitem{left}{right}

% Entry
\cventry{title}{institution}{location}{dates}{description}
```

## Tips

1. **Font Setup**: The custom template uses Helvetica Neue. For system fonts on macOS, XeLaTeX/LuaLaTeX works best.

2. **Bibliography**: For the moderncv version, create a `publications.bib` file and use `\bibliography{publications}`.

3. **Customization**: Modify the color definitions at the top of `cv-template.tex` to match your preference:
   ```latex
   \definecolor{primary}{RGB}{31, 73, 125}   % Header color
   \definecolor{accent}{RGB}{0, 112, 192}    % Accent color
   ```

4. **Page Margins**: Adjust in geometry package options:
   ```latex
   \usepackage[hmargin=0.75in, vmargin=0.75in]{geometry}
   ```

## Workflow for Updates

1. Update `cv-master` (markdown source of truth)
2. Sync changes to LaTeX template
3. Compile to PDF
4. Export specialized CVs (leadership, consulting, speaking) as needed
