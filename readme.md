

[![](https://user-images.githubusercontent.com/4236275/35933146-bfb7ec94-0c07-11e8-98d5-8972dc4b4e39.png)](hsttps://github.com/tonyfast/ten)

### [Github](hsttps://github.com/tonyfast/ten) | [NBViewer](http://nbviewer.jupyter.org/github/tonyfast/ten/blob/master/ten/intro.ipynb) | [Pages](https://tonyfast.github.io/ten)

[![Gitter](https://badges.gitter.im/tonyfast/ten.png)](https://gitter.im/tonyfast-ten)


Project Jupyter is a growing ecosystem of free, open source scientific software for interactive computing, consisting of millions of users and over a million notebooks on GitHub.  Jupyter's Notebook, and related experiences, are becoming standard interfaces for scientists and engineers.  The notebook interface is impacting the broader landscapes of research, computing, and teaching where data and code are essential; the stakeholders span industry, academia, and philanthropy.

This talk will review the history of Project Jupyter as scientific software born from the Scientific Python (SciPy) community.  Since it's inception, the community has extended Jupyter to work with over 50 different languages and provided new options for interactive development, research and presentation, including JupyterLab, the next generation of the Notebook.  In the broader open source community we find Jupyter tools for grading, batch processing, app development, documentation, tests, and even source code.


Within organizations, Jupyter notebooks are commonly used to exchange ideas and build knowledge bases across diverse disciplines.  The talk will highlight recent case studies in Jupyter transforming classroom education, massive collaboration in physics, and the entire multimedia experience of learning.



---

# Documentation

Create the [readme.md](https://github.com/noffle/art-of-readme "Styleguide for the future") and the documentation with nbconvert.

    if __name__ == '__main__':
        !jupyter nbconvert --MarkdownExporter.exclude_input=True --to markdown readme.ipynb
        !cp readme.md docs
        !jupyter nbconvert --MarkdownExporter.exclude_input=True --EmbedImagesPreprocessor.embed_images=True --to markdown ten/*.ipynb
        !mv ten/*.md docs
        !mv ten/technical_files/*.svg docs/technical_files
        !mv ten/history_files/*.svg docs/history_files
        !mv ten/collaboration_files/*.svg docs/collaboration_files/
        !rm -rf ten/*_files



## Test

This project aims to be readable, reusable, and reproducible literate documents created with Jupyter.  

    def testTheModules():
        """Import all of the modules created for ten, test for completeness."""
        with __import__('IPython').utils.capture.capture_output() as out:
            from ten import history, technical, collaboration, intro
            from ten.particles import kernels, refs as xx, computing, recent
        modules = history, technical, collaboration, recent, kernels, computing, intro
        assert the.map(lambda x: x.__complete__ is True).all()(modules)
        assert the.map(x.__file__).map(the.str.endswith('.ipynb')).all()(modules)
                
    assert not getattr(__name__ == '__main__' and unittest(testTheModules), 'errors', None), """The tests were run and did not pass""" 
