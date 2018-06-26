sequenceDiagram
  participant atom
  participant lilystitchUI
  participant lilystitch.ly
  participant lilycompile
  participant pdfview

  atom->>lilystitchUI: user installs/activates
  lilystitchUI->>atom: queries .ly files in project
  atom->>lilystitchUI: returns list of .ly files
  lilystitchUI->>atom: opens UI in display pane with box for each .ly file
  lilystitchUI->>lilystitch.ly: left to right box sequence written as include sequence in tmp .ly
  atom->>lilystitchUI: user clicks/drags boxes to rearrange
  lilystitchUI->>lilystitchUI: boxes re-render in new positions
  lilystitchUI->>lilystitch.ly: .ly rewritten to tmp to rearrange include statements
  lilystitch.ly-->>lilycompile: .ly for render and display  
  lilycompile-->>pdfview: .pdf for display
  pdfview-->>atom: displays .pdf in new tab
