# FAIR Principles

The FAIR principles (Findable, Accessible, Interoperable, Reusable) are a set of guidelines to improve the management and sharing of research data. These principles ensure that data is prepared in a way that optimizes its reuse and reproducibility.

### Findable

Data should be easy to find by both humans and computers. This involves assigning a globally unique and persistent identifier to data, describing data with rich metadata, and indexing metadata in searchable resources. Clear and explicit identifiers should be included in metadata to facilitate search and discovery.

### Accessible

Once data is found, it should be easy to access. This requires that data and metadata be retrievable via standardized communication protocols, which are open, free, and universally implementable. Where necessary, these protocols should support authentication and authorization. Additionally, metadata should remain accessible even if the data itself is no longer available.

### Interoperable

Data should be integrated with other data. This is achieved by using formal, accessible, shared, and widely applicable languages for knowledge representation. Data and metadata should use vocabularies that adhere to FAIR principles, and include qualified references to other data and metadata to ensure consistency and interoperability.

### Reusable

Data should be reusable for future research. This means data and metadata should be richly described with accurate and relevant attributes. Data should be released with clear and accessible usage licenses, associated with detailed provenance information, and conform to community standards relevant to the domain.

Adopting the FAIR principles in your research ensures that your data is well-managed, easily shared, and readily available for future research. More information about the FAIR principles can be found on the [GO FAIR website](https://www.go-fair.org/fair-principles/).


# Understanding BIDS for Neuroimaging Data

## Introduction to BIDS

**BIDS (Brain Imaging Data Structure)** is a standardized way to organize and describe neuroimaging and behavioral data. It simplifies the process of data sharing, analysis, and collaboration in the neuroscience community. BIDS is designed to make data easier to use and to facilitate reproducible research.

## Why Use BIDS?

BIDS offers several advantages:
- **Standardization**: Ensures data consistency across studies.
- **Interoperability**: Facilitates data sharing and collaboration.
- **Tool Compatibility**: Compatible with various neuroimaging analysis tools.
- **Reproducibility**: Promotes reproducible research practices.

For a detailed overview, you can visit the [official BIDS website](https://bids.neuroimaging.io/).

## Key Features of BIDS

1. **File Naming and Organization**: BIDS specifies a consistent naming convention and folder structure.
2. **Metadata**: Comprehensive metadata standards to describe data acquisition parameters.
3. **Data Types**: Supports various data types, including MRI, MEG, EEG, iEEG, and more.
4. **Extensions**: Allows for community-driven extensions to support new data types and modalities.

## Getting Started with BIDS

To start using BIDS, you can refer to the [BIDS Starter Kit](https://bids-standard.github.io/bids-starter-kit/). This resource provides templates, examples, and guidelines for converting your data to BIDS format.

## Converting Data to BIDS Format

To simplify the process of converting neuroimaging data to BIDS format, various software tools known as BIDS converters have been developed. A non-exhaustive list of available BIDS converters can be found [here](https://bids.neuroimaging.io/benefits).

Many of the original and most popular BIDS converters, such as **HeuDiConv** and **Dcm2Bids**, require users to create custom code to specify the mapping between their imaging data and resulting BIDS output. However, newer tools have been developed to minimize or eliminate the need for coding by making educated guesses about the data's identity and suggesting the appropriate BIDS information and structure. For example, **BIDScoin** offers a graphical user interface (GUI), making it user-friendly, while **ezBIDS** takes a web-based approach. These newer tools are particularly useful for researchers who are less familiar with BIDS or not well-versed in the syntax and structure of the older converters. While the older BIDS converters provide more flexibility, the newer tools are designed to be more accessible and easier to use.

## Tools for Working with BIDS Data

- **nipopy:** Lightweight neuroimaging workflow manager to help with DICOM to BIDS conversion and running BIDS apps
- **BIDS Validator**: A tool to ensure your dataset conforms to BIDS specifications. To acce
- **pyBIDS**: A Python library to query and manipulate BIDS datasets. Learn more in the [pyBIDS documentation](https://bids-standard.github.io/pybids/introduction.html#what-is-bids-and-why-should-you-use-it).
ss this tool, go to the [BIDS Validator webpage](https://bids-standard.github.io/bids-validator/)
- **BIDS Apps**: Once you have converted data BIDS, you are ready to begin using BIDS apps, which are a collection of neuroimaging data analysis pipelines that accept BIDS-formatted data as input, such as MRIQC and fMRIPrep. Learn more in the [BIDS App page](https://bids-apps.neuroimaging.io/)


## Detailed Guides and Tutorials

- **Andy's Brain Book BIDS Overview**: An introductory guide to BIDS, available on [Andy's Brain Book](https://andysbrainbook.readthedocs.io/en/latest/OpenScience/OS/BIDS_Overview.html).
- **RPubs Tutorial**: A comprehensive guide on BIDS with subsequent tutorials on using fMRIPrep and MRIQC, available on [RPubs](https://rpubs.com/sarenseeley/bids-fmriprep-mriqc).
- **OSF Guide**: A step-by-step guide to creating BIDS datasets, available on the [Open Science Framework](https://osf.io/dcbfj).

## Literature and Documentation

A detailed description of the development of BIDS and benefits, can be found in the foundational BIDS [paper published in Nature](https://www.nature.com/articles/sdata201644).

A description of how to build containerized apps supporting BIDS inputs can be found in the [paper published in PLOS Computational Biology](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005209).

For the official specification and in-depth documentation, refer to the [BIDS Specification](https://bids-specification.readthedocs.io/en/stable/).

## Conclusion

BIDS is a powerful standard that enhances the organization, sharing, and analysis of neuroimaging data. By adopting BIDS, researchers can improve the reproducibility of their studies and facilitate broader collaboration within the neuroscience community.

# NiPoppy

### Introduction to NiPoppy

**NiPoppy** is a robust, automated pipeline designed for the quality assessment of neuroimaging data. It is particularly useful for researchers working with large datasets, ensuring that data quality is consistently evaluated and maintained.

### Features of NiPoppy

NiPoppy offers a variety of features aimed at streamlining the quality assessment process:

- **Automated Quality Checks**: NiPoppy performs comprehensive quality checks on neuroimaging data, identifying potential issues and ensuring data integrity.
- **Compatibility**: It supports various neuroimaging data formats and integrates seamlessly with existing neuroimaging workflows.
- **Scalability**: NiPoppy is designed to handle large datasets, making it ideal for projects involving substantial amounts of neuroimaging data.

You can refer here for an [Overview of NiPoppy](https://neurobagel.org/nipoppy/overview/).

### Getting Started with NiPoppy

To begin using NiPoppy, you can refer to the [NiPoppy Documentation](https://nipoppy.readthedocs.io/en/latest/#). The documentation provides detailed instructions on installation, configuration, and usage, ensuring that researchers can quickly integrate NiPoppy into their workflows.

The [NiPoppy GitHub repository](https://github.com/nipoppy/nipoppy?tab=readme-ov-file) offers access to the source code, installation instructions, and additional resources. This is also a resource for developers and users looking to customize or contribute to the NiPoppy project.


### Conclusion

NiPoppy is a powerful tool for the automated quality assessment of neuroimaging data, offering significant advantages in terms of efficiency, scalability, and integration. By incorporating NiPoppy into your research, you can ensure the reliability and quality of your neuroimaging datasets, ultimately enhancing the robustness of your scientific findings.

