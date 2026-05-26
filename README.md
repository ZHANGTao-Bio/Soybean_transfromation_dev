# Soybean_transfromation_dev
Multi-omics analysis of soybean genetic transformation at different developmental stages
##目录结构
'''
~/
├── projects/                         # 所有项目根目录
│   └── project_name/                 # soybean_transformation_dev
│       ├── raw_data/                 # 原始测序数据（fastq / bam），强烈建议只读
│       ├── metadata/                 # 样本信息表、实验设计、批次信息等
│       ├── scripts/                  # 分析脚本（bash、R、Python、Snakemake等）
│       ├── results/                  # 最终结果（图表、报告、整合后的文件）
│       │
│       ├── WGBS/                     # 全基因组甲基化测序
│       │   ├── qc/                   # FastQC, MultiQC, 甲基化水平QC
│       │   ├── alignment/            # Bismark / BWA‑meth 比对结果（BAM）
│       │   ├── methylation_calling/  # CpG位点甲基化水平（cov, bedgraph）
│       │   └── diff_methylation/     # 差异甲基化区域（DMR）分析结果
│       │
│       ├── CUT&Tag/                  # 靶向蛋白/DNA互作（如组蛋白修饰）
│       │   ├── qc/                   # 片段长度分布、重复率、ENCODE质控指标
│       │   ├── alignment/            # bowtie2 / STAR 比对结果
│       │   ├── peaks/                # MACS2 / SEACR  peaks（narrowPeak, broadPeak）
│       │   └── footprinting/         # 足迹分析（如HINT‑ATAC）及Motif富集
│       │
│       ├── snRNA_seq/                # 单细胞核RNA测序
│       │   ├── qc/                   # 细胞/基因质控过滤指标
│       │   ├── cellranger/           # Cell Ranger 输出（outs/）或 STARsolo结果
│       │   ├── seurat/               # Seurat对象（RDS）、聚类、差异表达
│       │   └── trajectory/           # 拟时序/轨迹推断（monocle, slingshot）
│       │
│       └── snATAC_seq/               # 单细胞ATAC测序
│           ├── qc/                   # 片段富集、TSS富集得分、双细胞剔除
│           ├── cellranger_atac/      # Cell Ranger ATAC 输出
│           ├── archr/                # ArchR 分析流程（Arrow文件、聚类、差异peak）
│           └── integration/          # 与snRNA‑seq的多组学整合（Seurat WNN, MOFA+）
│
├── software/                         # 软件安装目录（如 miniconda3、容器、mamba环境）
├── databases/                        # 全局参考数据（可软链接到各个项目）
│   ├── genome/                       # 参考基因组（hg38, mm10, etc.）
│   │   ├── hg38/                     # 包括 .fa, .gtf, .bowtie2_index, .bismark_index
│   │   └── mm10/
│   └── annotation/                   # 额外注释（CpG岛、重复元件、黑名单区域）
│
└── tmp/                              # 临时文件（注意定期清理）
'''
