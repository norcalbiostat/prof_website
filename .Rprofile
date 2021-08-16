options(blogdown.author = "Robin Donatello",
        blogdown.ext = ".Rmarkdown",
        blogdown.subdir = "post",
        blogdown.yaml.empty = TRUE,
        blogdown.new_bundle = TRUE,
        blogdown.title_case = TRUE)

rprofile <- Sys.getenv("R_PROFILE_USER", "~/.Rprofile")
if (file.exists(rprofile)) {
  source(file = rprofile)
}

# fix Hugo version
options(blogdown.hugo.version = "0.84.1")
