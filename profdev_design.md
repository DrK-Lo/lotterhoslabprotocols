# Design

**Access NU Creative Cloud:** We have access to In Design, Illustrator, Photoshop, and Adobe Pro (for editing pdfs). 
Here is how to access the [Adobe Creative Cloud](https://adobe.northeastern.edu/) and 
make sure to [follow the instructions here](https://service.northeastern.edu/ogs?id=kb_article&sys_id=4128ecdb1b42745069590dc1604bcbb2) (choose “active directory”)

**Guidance and resources**

[Aug 31 2021 Lab meeting recording - Data Viz discussion from the NU specialist](https://northeastern.zoom.us/rec/share/L4GY5DKi6XCi1nf8_RxkzyGyu6NAojZd4nsNsL1WpxiEfNp5qe_PHd5An9ngPANS.49r97rNHCjo5PNSH) (ask Katie for password)

* [NU library page on data visualization resources](https://subjectguides.lib.neu.edu/dataviz/tutorials)

**Templates**

[A Keynote color/font template for presentations and posters](https://github.com/DrK-Lo/lotterhoslabprotocols/raw/gh-pages/ClassicPresentationTheme.key)

**A ggtheme for graphs with white backgrounds and dark grey lines**

```
ggtheme <- theme_bw() + theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(), 
panel.background = element_blank(), panel.border=element_blank(), axis.line = element_line(colour=“grey30”), 
axis.title = element_text(colour=“grey20”), axis.text = (element_text(colour=“grey30”)), 
legend.title = element_text(colour=“grey20”), legend.text = element_text(colour=“grey30”))
```
