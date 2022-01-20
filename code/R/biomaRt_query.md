creating_biomaRt_query
================
Balint_Biro
1/20/2022

``` r
#There are two possible way to install biomaRt library
#install.packages('BiocManager',quietly=TRUE)
#BiocManager::install('biomaRt')
```

``` r
#loading the library
library(biomaRt)
```

``` r
#First, the desired database (DB) should be called. Check all the available DBs
#in our qery the DB is gonna be called biomart
listEnsembl()
```

    ##         biomart                version
    ## 1         genes      Ensembl Genes 105
    ## 2 mouse_strains      Mouse strains 105
    ## 3          snps  Ensembl Variation 105
    ## 4    regulation Ensembl Regulation 105

``` r
#DB1-GENES
#select the desired dataset. To list the available datasets, first you have to
#specify your biomart (aka DB) and the preferred DB mirror (useast,uswest,asia
#and www)
ensembl <- useEnsembl(biomart='genes',
                      mirror='useast')
head(listDatasets(ensembl))
```

    ##                        dataset                           description
    ## 1 abrachyrhynchus_gene_ensembl Pink-footed goose genes (ASM259213v1)
    ## 2     acalliptera_gene_ensembl      Eastern happy genes (fAstCal1.2)
    ## 3   acarolinensis_gene_ensembl       Green anole genes (AnoCar2.0v2)
    ## 4    acchrysaetos_gene_ensembl       Golden eagle genes (bAquChr1.2)
    ## 5    acitrinellus_gene_ensembl        Midas cichlid genes (Midas_v5)
    ## 6    amelanoleuca_gene_ensembl       Giant panda genes (ASM200744v2)
    ##       version
    ## 1 ASM259213v1
    ## 2  fAstCal1.2
    ## 3 AnoCar2.0v2
    ## 4  bAquChr1.2
    ## 5    Midas_v5
    ## 6 ASM200744v2

``` r
#DB2-MOUSE STRAINS
#select the desired dataset. To list the available datasets, first you have to
#specify your biomart (aka DB) and the preferred DB mirror (useast,uswest,asia
#and www)
ensembl <- useEnsembl(biomart='mouse_strains',
                      mirror='useast')
head(listDatasets(ensembl))
```

    ##                     dataset                              description
    ## 1 mm129s1svimj_gene_ensembl Mouse 129S1/SvImJ genes (129S1_SvImJ_v1)
    ## 2         mmaj_gene_ensembl                 Mouse A/J genes (A_J_v1)
    ## 3       mmakrj_gene_ensembl             Mouse AKR/J genes (AKR_J_v1)
    ## 4     mmbalbcj_gene_ensembl         Mouse BALB/cJ genes (BALB_cJ_v1)
    ## 5     mmc3hhej_gene_ensembl         Mouse C3H/HeJ genes (C3H_HeJ_v1)
    ## 6   mmc57bl6nj_gene_ensembl     Mouse C57BL/6NJ genes (C57BL_6NJ_v1)
    ##          version
    ## 1 129S1_SvImJ_v1
    ## 2         A_J_v1
    ## 3       AKR_J_v1
    ## 4     BALB_cJ_v1
    ## 5     C3H_HeJ_v1
    ## 6   C57BL_6NJ_v1

``` r
#DB3-SNPS
#select the desired dataset. To list the available datasets, first you have to
#specify your biomart (aka DB) and the preferred DB mirror (useast,uswest,asia
#and www)
ensembl <- useEnsembl(biomart='snps',
                      mirror='useast')
head(listDatasets(ensembl))
```

    ##                  dataset
    ## 1            btaurus_snp
    ## 2      btaurus_structvar
    ## 3            chircus_snp
    ## 4       clfamiliaris_snp
    ## 5 clfamiliaris_structvar
    ## 6             drerio_snp
    ##                                                                      description
    ## 1   Cow Short Variants (SNPs and indels excluding flagged variants) (ARS-UCD1.2)
    ## 2                                           Cow Structural Variants (ARS-UCD1.2)
    ## 3        Goat Short Variants (SNPs and indels excluding flagged variants) (ARS1)
    ## 4 Dog Short Variants (SNPs and indels excluding flagged variants) (ROS_Cfam_1.0)
    ## 5                                         Dog Structural Variants (ROS_Cfam_1.0)
    ## 6 Zebrafish Short Variants (SNPs and indels excluding flagged variants) (GRCz11)
    ##        version
    ## 1   ARS-UCD1.2
    ## 2   ARS-UCD1.2
    ## 3         ARS1
    ## 4 ROS_Cfam_1.0
    ## 5 ROS_Cfam_1.0
    ## 6       GRCz11

``` r
#DB4-REGULATION
#select the desired dataset. To list the available datasets, first you have to
#specify your biomart (aka DB) and the preferred DB mirror (useast,uswest,asia
#and www)
ensembl <- useEnsembl(biomart='regulation',
                      mirror='useast')
head(listDatasets(ensembl))
```

    ##                          dataset                                 description
    ## 1      hsapiens_external_feature Human Other Regulatory Regions (GRCh38.p13)
    ## 2  hsapiens_mirna_target_feature     Human miRNA Target Regions (GRCh38.p13)
    ## 3                  hsapiens_peak      Human Regulatory Evidence (GRCh38.p13)
    ## 4    hsapiens_regulatory_feature      Human Regulatory Features (GRCh38.p13)
    ## 5     mmusculus_external_feature     Mouse Other Regulatory Regions (GRCm39)
    ## 6 mmusculus_mirna_target_feature         Mouse miRNA Target Regions (GRCm39)
    ##      version
    ## 1 GRCh38.p13
    ## 2 GRCh38.p13
    ## 3 GRCh38.p13
    ## 4 GRCh38.p13
    ## 5     GRCm39
    ## 6     GRCm39

``` r
#After you select the dataset then you need to specify the Attributes. For a
#nice example I picked mouse strains and the genes of aj strain. Attributes are
#basically the features that you wanna have as return values (that you are
#interested in i.e. gene name, protein name etc.)
#all Attributes
ensembl <- useEnsembl(biomart='mouse_strains',
                      dataset='mmaj_gene_ensembl',
                      mirror='useast')
head(listAttributes(ensembl))
```

    ##                            name                  description         page
    ## 1               ensembl_gene_id               Gene stable ID feature_page
    ## 2       ensembl_gene_id_version       Gene stable ID version feature_page
    ## 3         ensembl_transcript_id         Transcript stable ID feature_page
    ## 4 ensembl_transcript_id_version Transcript stable ID version feature_page
    ## 5            ensembl_peptide_id            Protein stable ID feature_page
    ## 6               ensembl_exon_id               Exon stable ID feature_page

``` r
#There is a bunch of different available attributes which can be quite
#tricky to go through if you are not sure what are you looking for so biomaRt
#offers a nice masking step to search for the appropriate attributes.
searchAttributes(mart=ensembl, pattern='go')
```

    ##                               name
    ## 27                           go_id
    ## 30                 go_linkage_type
    ## 32            goslim_goa_accession
    ## 33          goslim_goa_description
    ## 218    mmusculus_homolog_goc_score
    ## 233 mm129s1svimj_homolog_goc_score
    ## 248       mmakrj_homolog_goc_score
    ## 263     mmbalbcj_homolog_goc_score
    ## 278     mmc3hhej_homolog_goc_score
    ## 293   mmc57bl6nj_homolog_goc_score
    ## 308    mmcasteij_homolog_goc_score
    ## 323       mmcbaj_homolog_goc_score
    ## 338      mmdba2j_homolog_goc_score
    ## 353      mmfvbnj_homolog_goc_score
    ## 368        mmlpj_homolog_goc_score
    ## 383  mmnodshiltj_homolog_goc_score
    ## 398   mmnzohlltj_homolog_goc_score
    ## 413     mmpwkphj_homolog_goc_score
    ## 428     mmwsbeij_homolog_goc_score
    ## 443  rnorvegicus_homolog_goc_score
    ##                                         description         page
    ## 27                                GO term accession feature_page
    ## 30                            GO term evidence code feature_page
    ## 32                          GOSlim GOA Accession(s) feature_page
    ## 33                           GOSlim GOA Description feature_page
    ## 218             Mouse Gene-order conservation score     homologs
    ## 233 Mouse 129S1/SvImJ Gene-order conservation score     homologs
    ## 248       Mouse AKR/J Gene-order conservation score     homologs
    ## 263     Mouse BALB/cJ Gene-order conservation score     homologs
    ## 278     Mouse C3H/HeJ Gene-order conservation score     homologs
    ## 293   Mouse C57BL/6NJ Gene-order conservation score     homologs
    ## 308    Mouse CAST/EiJ Gene-order conservation score     homologs
    ## 323       Mouse CBA/J Gene-order conservation score     homologs
    ## 338      Mouse DBA/2J Gene-order conservation score     homologs
    ## 353      Mouse FVB/NJ Gene-order conservation score     homologs
    ## 368        Mouse LP/J Gene-order conservation score     homologs
    ## 383  Mouse NOD/ShiLtJ Gene-order conservation score     homologs
    ## 398   Mouse NZO/HlLtJ Gene-order conservation score     homologs
    ## 413     Mouse PWK/PhJ Gene-order conservation score     homologs
    ## 428     Mouse WSB/EiJ Gene-order conservation score     homologs
    ## 443               Rat Gene-order conservation score     homologs

``` r
#In the last step before the query you have to specify the Filters. The Filters
#are gonna determine the input for the query.
#all Filters
head(listAttributes(ensembl))
```

    ##                            name                  description         page
    ## 1               ensembl_gene_id               Gene stable ID feature_page
    ## 2       ensembl_gene_id_version       Gene stable ID version feature_page
    ## 3         ensembl_transcript_id         Transcript stable ID feature_page
    ## 4 ensembl_transcript_id_version Transcript stable ID version feature_page
    ## 5            ensembl_peptide_id            Protein stable ID feature_page
    ## 6               ensembl_exon_id               Exon stable ID feature_page

``` r
#The situation is kinda same as it was at the Attributes when it comes to
#Filters so scrolling through a ton of Filters is filthy. But there is also a
#masking possibility
searchFilters(mart=ensembl, pattern='gene')
```

    ##                              name
    ## 8   with_clone_based_ensembl_gene
    ## 10     with_clone_based_vega_gene
    ## 12     with_entrezgene_trans_name
    ## 24                with_entrezgene
    ## 27             with_reactome_gene
    ## 38                   with_unigene
    ## 44                  with_wikigene
    ## 45                ensembl_gene_id
    ## 46        ensembl_gene_id_version
    ## 51             external_gene_name
    ## 54       clone_based_ensembl_gene
    ## 56          clone_based_vega_gene
    ## 58          entrezgene_trans_name
    ## 71           entrezgene_accession
    ## 72                  entrezgene_id
    ## 75                  reactome_gene
    ## 86                        unigene
    ## 93                  wikigene_name
    ## 94                    wikigene_id
    ## 104    with_affy_mogene_1_0_st_v1
    ## 105    with_affy_mogene_2_1_st_v1
    ## 128         affy_mogene_1_0_st_v1
    ## 129         affy_mogene_2_1_st_v1
    ## 147                        source
    ## 170                   with_gene3d
    ## 186                        gene3d
    ##                                                 description
    ## 8                     With Clone-based (Ensembl) gene ID(s)
    ## 10                       With Clone-based (Vega) gene ID(s)
    ## 12                    With EntrezGene transcript name ID(s)
    ## 24                                     With NCBI gene ID(s)
    ## 27                                 With Reactome gene ID(s)
    ## 38                                       With UniGene ID(s)
    ## 44                                      With WikiGene ID(s)
    ## 45                 Gene stable ID(s) [e.g. MGP_AJ_G0000001]
    ## 46  Gene stable ID(s) with version [e.g. MGP_AJ_G0000001.1]
    ## 51                                   Gene Name(s) [e.g. Ky]
    ## 54       Clone-based (Ensembl) gene ID(s) [e.g. AC149090.1]
    ## 56       Clone-based (Vega) gene ID(s) [e.g. RP23-325D10.3]
    ## 58      EntrezGene transcript name ID(s) [e.g. Olfr512-201]
    ## 71              NCBI gene accession(s) [e.g. 0610007P14Rik]
    ## 72                         NCBI gene ID(s) [e.g. 100009600]
    ## 75                  Reactome gene ID(s) [e.g. R-MMU-109581]
    ## 86                               UniGene ID(s) [e.g. Mm.10]
    ## 93                    WikiGene name(s) [e.g. 0610007P14Rik]
    ## 94                          WikiGene ID(s) [e.g. 100009600]
    ## 104                  With AFFY MoGene 1 0 st v1 probe ID(s)
    ## 105                  With AFFY MoGene 2 1 st v1 probe ID(s)
    ## 128       AFFY MoGene 1 0 st v1 probe ID(s) [e.g. 10588203]
    ## 129       AFFY MoGene 2 1 st v1 probe ID(s) [e.g. 17520835]
    ## 147                                           Source (gene)
    ## 170                                       With Gene3D ID(s)
    ## 186                          Gene3D ID(s) [e.g. 1.10.10.10]

``` r
#create the biomaRt query by using the previously detailed steps
#attributes are gonna be your return values (output)
#filters are the names of your input
#values are the actual inputs
#mart is the data where we specified the DB and Dataset
data <- getBM(attributes=c('external_gene_name','uniprotswissprot','go_id'),
                 filters=c('chromosomal_region'),
                 values=list('1:1230000:1450000'),
              mart=ensembl)
head(data)
```

    ##   external_gene_name uniprotswissprot      go_id
    ## 1                                               
    ## 2                Rp1           P56716 GO:0097542
    ## 3                Rp1           P56716 GO:0005875
    ## 4                Rp1           P56716 GO:0001750
    ## 5                Rp1           P56716 GO:0046785
    ## 6                Rp1           P56716 GO:0045494
