
begin
  require "#{dir = File.dirname(__FILE__)}/task/gemgem"
rescue LoadError
  sh 'git submodule update --init'
  exec Gem.ruby, '-S', $PROGRAM_NAME, *ARGV
end

Gemgem.init(dir) do |s|
  require 'jellyfish/version'
  s.name    = 'jellyfish'
  s.version = Jellyfish::VERSION
  %w[rack bacon muack].each{ |g| s.add_development_dependency(g) }
end
