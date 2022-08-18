dnl run `autoreconf -i` to generate a configure script. 
dnl Then run ./configure to generate a Makefile.
dnl Finally run make to generate the project.

AC_INIT([py2guile], [0.9.0],
        [arne_bab@web.de])
# Check for programs I need for my build
AC_CANONICAL_TARGET
AC_ARG_VAR([emacs], [How to call Emacs.])
AC_CHECK_TARGET_TOOL([emacs], [emacs], [no])
AC_ARG_VAR([ebookconvert], [How to call ebook-convert from calibre.])
AC_CHECK_TARGET_TOOL([ebookconvert], [ebook-convert], [no])
AC_ARG_VAR([pandoc], [How to call pandoc.])
AC_CHECK_TARGET_TOOL([pandoc], [pandoc], [no])
AS_IF([test "x$emacs" = "xno"], [AC_MSG_ERROR([cannot find Emacs.])])
AS_IF([test "x$ebookconvert" = "xno"], [AC_MSG_ERROR([cannot find ebook-convert which is part of the calibre tools.])])
AS_IF([test "x$pandoc" = "xno"], [AC_MSG_ERROR([cannot find pandoc.])])
dnl provide mkdir -p as ${MKDIR_P} to the Makefile
AC_PROG_MKDIR_P
# Run automake
dnl use tar-pax to allow for arbitrary length filenames
AM_INIT_AUTOMAKE([gnu tar-pax])
AM_MAINTAINER_MODE([enable])
AC_CONFIG_FILES([Makefile])
# the large image is not explicitly needed, but should be included as high quality source file.
AC_CONFIG_LINKS([green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-4533044418_707b0029b2_o.jpg:green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-4533044418_707b0029b2_o.jpg green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-800x600.jpg:green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-800x600.jpg green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-and-guile-gnu-goatee-gnu-author-martin-grabmueller-license-gplv3-or-later-800x600.jpg:green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-and-guile-gnu-goatee-gnu-author-martin-grabmueller-license-gplv3-or-later-800x600.jpg guile-gnu-goatee.jpg:guile-gnu-goatee.jpg green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-4533044418_707b0029b2_o-and-guile-gnu-goatee-by-martin-grabmueller-license-gplv3-or-later-unified-resynth.jpg:green_tree_python-flickr-author-msvg-michael_gil-license-cc_by-4533044418_707b0029b2_o-and-guile-gnu-goatee-by-martin-grabmueller-license-gplv3-or-later-unified-resynth.jpg py2guile.org:py2guile.org htmlize.el:htmlize.el wisp-mode.el:wisp-mode.el gpl.tex:gpl.tex])
AC_OUTPUT
