require "slim"
require "sassc"

namespace :compile do
  desc "Compile Slim to HTML"
  task :slim do
    Dir.glob("src/**/*.slim").each do |file|
      html = Slim::Template.new(file).render
      File.write("dist/#{File.basename(file, ".slim")}.html", html)
      puts "Compiled #{file} to HTML!"
    end
  end

  desc "Compile Sass to CSS"
  task :sass do
    Dir.glob("src/**/*.scss").each do |file|
      css = SassC::Engine.new(File.read(file)).render
      File.write("dist/#{File.basename(file, ".scss")}.css", css)
      puts "Compiled #{file} to CSS!"
    end
  end
end
