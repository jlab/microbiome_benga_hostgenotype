PNGDPI=300

SVGFILES = $(wildcard fig*.svg)

figures = PDF/GA.pdf \
	  PDF/fig1_breedingStrategy.pdf \
	  PDF/fig3_gutDiversity.pdf \
	  PDF/fig2_gutTemporal.pdf \
	  PDF/fig5_skinTemporal.pdf \
	  PDF/fig6_gutTaxonomy.pdf \
	  PDF/fig4_gutEffectSizes.pdf \
	  PDF/fig7_metabolites.pdf \
	  PDF/figS1_emperorSkinGut.pdf \
	  PDF/figS2_skinDiversity.pdf \
	  PDF/figS3_gutAlpha.pdf \
	  PDF/figS4_skinAlpha.pdf \
	  PDF/figS5_gutGenera.pdf \
	  PDF/figS6_skinGenera.pdf \
	  PDF/figS7_taxBarplots.pdf \
	  PDF/figS8_skinSourceTracking.pdf \
	  PDF/figS9_taxonomyRobertson.pdf
figpng = $(figures:.pdf=.png)

pdf: $(figures)
	pdfunite $(figures) figures.pdf;
png: $(subst PDF,PNG,$(figpng))


PDF/fig1_breedingStrategy.pdf: fig1_breedingStrategy.pdf
	cp fig1_breedingStrategy.pdf PDF/

PNG/fig1_breedingStrategy.png: fig1_breedingStrategy.pdf
	convert $< $@

PDF/%.pdf: %.svg
	mkdir -p `dirname $@`
	inkscape -d $(PNGDPI) -C --export-type=pdf -o $@ $<
	
PDF/%.pdf: %.jpg
	mkdir -p `dirname $@`
	convert $< $@;

PNG/%.png: %.jpg
	mkdir -p `dirname $@`
	convert $< $@;

PNG/%.png: %.svg
	mkdir -p `dirname $@`
	inkscape -d $(PNGDPI) -C --export-type=png -o $@ $<
