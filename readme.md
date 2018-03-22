

[![](https://user-images.githubusercontent.com/4236275/35933146-bfb7ec94-0c07-11e8-98d5-8972dc4b4e39.png)](hsttps://github.com/tonyfast/ten)

### [Github](hsttps://github.com/tonyfast/ten) | [NBViewer](http://nbviewer.jupyter.org/github/tonyfast/ten/blob/master/ten/intro.ipynb) | [Pages](https://tonyfast.github.io/ten)

[![Gitter](https://badges.gitter.im/tonyfast/ten.png)](https://gitter.im/tonyfast-ten)


Project Jupyter is a growing ecosystem of free, open source scientific software for interactive computing, consisting of millions of users and over a million notebooks on GitHub.  Jupyter's Notebook, and related experiences, are becoming standard interfaces for scientists and engineers.  The notebook interface is impacting the broader landscapes of research, computing, and teaching where data and code are essential; the stakeholders span industry, academia, and philanthropy.

This talk will review the history of Project Jupyter as scientific software born from the Scientific Python (SciPy) community.  Since it's inception, the community has extended Jupyter to work with over 50 different languages and provided new options for interactive development, research and presentation, including JupyterLab, the next generation of the Notebook.  In the broader open source community we find Jupyter tools for grading, batch processing, app development, documentation, tests, and even source code.


Within organizations, Jupyter notebooks are commonly used to exchange ideas and build knowledge bases across diverse disciplines.  The talk will highlight recent case studies in Jupyter transforming classroom education, massive collaboration in physics, and the entire multimedia experience of learning.



# [Get Started](ten/intro.ipynb)



---

# Documentation

Create the [readme.md](https://github.com/noffle/art-of-readme "Styleguide for the future") and the documentation with nbconvert.

    if __name__ == '__main__':
        !jupyter nbconvert --MarkdownExporter.exclude_input=True --to markdown readme.ipynb
        !cp readme.md docs
        !source activate p6 && jupyter nbconvert --MarkdownExporter.exclude_input=True --execute --to markdown ten/*.ipynb
        !mv ten/*.md docs
        !mv ten/technical_files/*.svg docs/technical_files
        !mv ten/history_files/*.svg docs/history_files
        !mv ten/collaboration_files/*.svg docs/collaboration_files/
        !rm -rf ten/*_files


    [NbConvertApp] Converting notebook readme.ipynb to markdown
    [NbConvertApp] Writing 1755 bytes to readme.md
    [NbConvertApp] Converting notebook ten/collaboration.ipynb to markdown
    [NbConvertApp] Executing notebook with kernel: other-env
    [NbConvertApp] Support files will be in collaboration_files/
    [NbConvertApp] Making directory ten/collaboration_files
    [NbConvertApp] Making directory ten/collaboration_files
    [NbConvertApp] Making directory ten/collaboration_files
    [NbConvertApp] Writing 12661 bytes to ten/collaboration.md
    [NbConvertApp] Converting notebook ten/history.ipynb to markdown
    [NbConvertApp] Executing notebook with kernel: other-env
    [NbConvertApp] Support files will be in history_files/
    [NbConvertApp] Making directory ten/history_files
    [NbConvertApp] Making directory ten/history_files
    [NbConvertApp] Making directory ten/history_files
    [NbConvertApp] Making directory ten/history_files
    [NbConvertApp] Writing 34073 bytes to ten/history.md
    [NbConvertApp] Converting notebook ten/index.ipynb to markdown
    [NbConvertApp] Executing notebook with kernel: other-env
    [NbConvertApp] Support files will be in index_files/
    [NbConvertApp] Making directory ten/index_files
    [NbConvertApp] Writing 8618 bytes to ten/index.md
    [NbConvertApp] Converting notebook ten/technical.ipynb to markdown
    [NbConvertApp] Executing notebook with kernel: other-env
    [NbConvertApp] Support files will be in technical_files/
    [NbConvertApp] Making directory ten/technical_files
    [NbConvertApp] Making directory ten/technical_files
    [NbConvertApp] Making directory ten/technical_files
    [NbConvertApp] Making directory ten/technical_files
    [NbConvertApp] Writing 25245 bytes to ten/technical.md



## Test

This project aims to be readable, reusable, and reproducible literate documents created with Jupyter.  

    def testTheModules():
        """Import all of the modules created for ten, test for completeness."""
        with __import__('IPython').utils.capture.capture_output() as out:
            from ten import history, technical, collaboration, index
            from ten.particles import kernels, refs as xx, computing, recent
        modules = history, technical, collaboration, recent, kernels, computing, intro
        assert the.map(lambda x: x.__complete__ is True).all()(modules)
        assert the.map(x.__file__).map(the.str.endswith('.ipynb')).all()(modules)
                
    assert not getattr(__name__ == '__main__' and unittest(testTheModules), 'errors', None) , """The tests were run and did not pass""" 
    print("""🏆🏆🏆""")


    🏆🏆🏆

