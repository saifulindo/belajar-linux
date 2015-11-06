require "rubygems"
require "tmpdir"

#require "bundler/setup"
require "jekyll"


# Change your GitHub reponame eg. "kippt/jekyll-incorporated"
GITHUB_REPONAME = "saifulindo/belajar-linux"


# namespace :site do
  desc "Generate blog files"
  task :generate do
    Jekyll::Site.new(Jekyll.configuration({
      "source"      => ".",
      "destination" => "_site"
    })).process
  end


  desc "Generate and publish blog to gh-pages"
  task :publish => [:generate] do
    Dir.mktmpdir do |tmp|
      cp_r "_site/.", tmp
      pwd = Dir.pwd
      Dir.chdir tmp
      system "git init"
      system "git add --all"
      message = "Site updated at #{Time.now}"
      system "git commit -m #{message.inspect}"
      system "git remote add origin git@github.com:#{GITHUB_REPONAME}.git"
#     system "git push origin master:refs/heads/gh-pages --force"
      system "git push origin master:refs/heads/master --force"
#      system "git push origin master --force"
      Dir.chdir pwd
    end
  end
# end
