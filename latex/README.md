# LaTeX CV Templates

Professional LaTeX templates for Shawn M. Vuong, MD.

## Templates

### cv-template.tex (Recommended)
Single-column professional academic CV.
- Full control over formatting
- Traditional academic layout
- 11 pages, 80KB

```bash
lualatex cv-template.tex
```

### cv-altacv.tex
Two-column CV with sidebar using AltaCV class.
- Modern sidebar design
- Two-column layout
- 61KB

```bash
lualatex cv-altacv.tex
```

**Note:** Requires `altacv.cls` in the same directory.

## Requirements

Both templates require LuaLaTeX:
```bash
lualatex cv-template.tex
```

## Current Status

- **Recommended:** `cv-template.tex` - single column, production-ready
- `cv-altacv.tex` - two-column alternative (more development needed)

## Custom Template Commands (cv-template.tex)

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

## Customization

### Colors
Edit the color definitions at the top of `cv-template.tex`:
```latex
\definecolor{primary}{RGB}{31, 73, 125}   % Header color
\definecolor{accent}{RGB}{0, 112, 192}    % Accent color
```

### Personal Information
Update these macros:
```latex
\newcommand{\CVname}{Shawn M. Vuong, MD}
\newcommand{\CVtitle}{Pediatric Neurosurgeon}
```

## Workflow

1. Update `cv-master` (markdown source of truth)
2. Sync changes to LaTeX template
3. Compile to PDF
4. Export specialized CVs (leadership, consulting, speaking) as needed
