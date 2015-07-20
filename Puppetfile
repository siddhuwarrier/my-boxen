# This file manages Puppet module dependencies.
#
# It works a lot like Bundler. We provide some core modules by
# default. This ensures at least the ability to construct a basic
# environment.

# Shortcut for a module from GitHub's boxen organization
def github(name, *args)
  options ||= if args.last.is_a? Hash
    args.last
  else
    {}
  end

  if path = options.delete(:path)
    mod name, :path => path
  else
    version = args.first
    options[:repo] ||= "boxen/puppet-#{name}"
    mod name, version, :github_tarball => options[:repo]
  end
end

# Shortcut for a module under development
def dev(name, *args)
  mod "puppet-#{name}", :path => "#{ENV['HOME']}/src/boxen/puppet-#{name}"
end

# Includes many of our custom types and providers, as well as global
# config. Required.

github "boxen", "3.10.4"

# Support for default hiera data in modules

github "module_data", "0.0.3", :repo => "ripienaar/puppet-module-data"

# Core modules for a basic development environment. You can replace
# some/most of these if you want, but it's not recommended.

github "brewcask",    "0.0.6"
github "gcc",         "2.2.1"
github "git",         "2.7.9"
github "homebrew",    "1.12.0"
github "nodejs",      "4.0.1"
github "openssl",     "1.0.0"
github "ruby",        "8.5.2"

# For Puppet
github "inifile",     "1.1.1", :repo => "puppetlabs/puppetlabs-inifile"
github "stdlib",      "4.2.1", :repo => "puppetlabs/puppetlabs-stdlib"
github "repository",  "2.4.1"
github "sudo",        "1.0.0"

#Additional modules
github "mongodb",     "1.4.0"
github "java",        "2.0.0", :repo => "siddhuwarrier/puppet-java"
