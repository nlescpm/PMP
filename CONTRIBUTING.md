# Contributing to Project Management Protocol

Thank you for your interest in contributing to the Netherlands eScience Center's Project Management Protocol! 

## Contribution Policy

**Primary Contributors**: We primarily accept contributions from Netherlands eScience Center employees, as this protocol reflects our internal practices and procedures.

**External Suggestions**: We welcome suggestions and feedback from the broader community! If you're external to the organization, please:
- Open an issue to discuss your suggestion
- Provide context for how the improvement would benefit eScience projects
- Note that final decisions on incorporating external suggestions rest with eScience Center staff

This document provides guidelines for contributing to the project.

## How to Contribute

### Before You Start

1. **Review existing issues** to see if your idea is already being discussed
2. **Open an issue** to discuss your proposed changes and get agreement on how it should be addressed in the PMP
3. **Read the current document** to understand the existing structure and style

### Making Changes

1. **Fork the repository** on GitHub
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/yourusername/PMP.git
   cd PMP
   ```
3. **Create a feature branch** from main:
   ```bash
   git checkout -b feature/improvement-description
   ```
4. **Make your changes**:
   - Edit the relevant `.tex` files in the `tex/` directory
   - Update bibliography in `references.bib` if needed
   - Add any new images to the `img/` directory
5. **Test compilation** to ensure your changes don't break the build:
   ```bash
   latexmk -xelatex main.tex
   ```
6. **Commit your changes** with a descriptive message:
   ```bash
   git commit -am 'Add improvement: description of changes'
   ```
   - Reference the issue number using `addresses #123` or `closes #123`
7. **Push to your branch**:
   ```bash
   git push origin improvement/improvement-description
   ```
8. **Create a Pull Request** on GitHub and reference the issues it addresses

### Guidelines

#### Content Guidelines

- **Be concise and clear**: The protocol should be practical and easy to follow
- **Use consistent terminology**: Follow the existing vocabulary and definitions
- **Provide examples**: Where appropriate, include concrete examples
- **Consider all project types**: Ensure guidelines work for different kinds of eScience projects

#### Style Guidelines

- **Follow existing formatting**: Match the style of existing sections
- **Use proper LaTeX**: Follow LaTeX best practices and use semantic markup
- **Test compilation**: Always verify that your changes compile successfully
- **Check for typos**: Proofread your contributions carefully

#### Technical Guidelines

- **File organization**: Keep content in appropriate `.tex` files within the `tex/` directory
- **Image format**: Use vector formats (PDF, SVG) when possible for figures
- **Bibliography**: Use proper BibTeX entries in `references.bib`
- **Hyperlinks**: Ensure all cross-references and external links work correctly

### Types of Contributions

We welcome various types of contributions:

- **Content improvements**: Better explanations, additional examples, clarifications
- **New sections**: Coverage of new aspects of project management
- **Bug fixes**: Corrections to errors, typos, or broken references
- **Formatting improvements**: Better layout, tables, figures
- **Documentation updates**: Improvements to README, this guide, or comments

### Review Process

1. **Automated checks**: Your PR will be automatically checked for compilation
2. **Content review**: Maintainers will review the content for accuracy and fit
3. **Style review**: We'll check that the changes follow our style guidelines
4. **Discussion**: We may ask questions or request changes
5. **Approval**: Once approved, your changes will be merged

### Getting Help

If you need help with:
- **LaTeX issues**: Check the [LaTeX documentation](https://www.latex-project.org/help/documentation/) or ask in the issue
- **Content questions**: Open an issue to discuss before making changes
- **Technical problems**: Describe your environment and the specific error you're encountering

### Code of Conduct

Please be respectful and constructive in all interactions. We're all working together to improve project management practices at the Netherlands eScience Center.

## Questions?

If you have questions about contributing, please:
1. Check if your question is answered in this guide
2. Look at existing issues and pull requests
3. Open a new issue with your question

Thank you for helping to improve the Project Management Protocol!
