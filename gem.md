### FAQ
#### gem_home vs gem_path
      GEM_PATH provides the locations (there may be several) where gems can be found.
      GEM_HOME is where gems will be installed (by default).
      (Therefore GEM_PATH should include GEM_HOME).
#### How to list gem configuration
      option1: run "gem enivronment"
      option2: for chef's embedded gem, may run "chef exec gem environment"
      option3: for chef's embedded gem, may run "chef shell-init bash". This output is like
            export PATH="/opt/chefdk/bin:/Users/jwan/.chefdk/gem/ruby/2.3.0/bin:/opt/chefdk/embedded/bin:/usr/local/Cellar/ruby/2.4.1_1/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/chefdk/gitbin"
            export GEM_ROOT="/opt/chefdk/embedded/lib/ruby/gems/2.3.0"
            export GEM_HOME="/Users/jwan/.chefdk/gem/ruby/2.3.0"
            export GEM_PATH="/Users/jwan/.chefdk/gem/ruby/2.3.0:/opt/chefdk/embedded/lib/ruby/gems/2.3.0"
            _chef_comp() {
                local COMMANDS="exec env gem generate shell-init install update push push-archive show-policy diff provision export clean-policy-revisions clean-policy-cookbooks delete-policy-group delete-policy undelete verify"
                COMPREPLY=($(compgen -W "$COMMANDS" -- ${COMP_WORDS[COMP_CWORD]} ))
            }
            complete -F _chef_comp chef
#### How to change gem configuration?
      option1: just put the following in your .profile (Max OS) or .bashrc (Linux)
            export GEM_PATH=/Users/myusername/Tools/.rbenv/versions/2.1.0/lib/ruby/gems/2.1.0
            export GEM_SPEC_CACHE=/Users/myusername/Tools/.rbenv/versions/2.1.0/lib/ruby/gems/specs
      option2: edit ~/.gemrc
            syntax:
                  :sources: A YAML array of remote gem repositories to install gems from
                  :verbose: Verbosity of the gem command. false, true, and :really are the level
                  :update_sources: Enable/disable automatic updating of repository metadata
                  :backtrace: Print backtrace when RubyGems encounters an error
                  :gempath: The paths in which to look for gems
                  :disable_default_gem_server: Force specification of gem server host on push
                  <gem_command>: A string containing arguments for the specified gem command
            sample:
                  :verbose: false
                  install: --no-wrappers
                  update: --no-wrappers
                  :disable_default_gem_server: true


### CLI reference (http://guides.rubygems.org/command-reference/#gem-environment)
#### gem build
#### gem cert
#### gem check
#### gem cleanup
#### gem contents
#### gem dependency
#### gem environment
      - RUBYGEMS VERSION: 2.1.5
      - RUBY VERSION: 2.0.0 (2013-06-27 patchlevel 247) [x86_64-darwin12.4.0]
      - INSTALLATION DIRECTORY: /Users/ttm/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0
      - RUBY EXECUTABLE: /Users/ttm/.rbenv/versions/2.0.0-p247/bin/ruby
      - EXECUTABLE DIRECTORY: /Users/ttm/.rbenv/versions/2.0.0-p247/bin
      - SPEC CACHE DIRECTORY: /Users/ttm/.gem/specs
      - RUBYGEMS PLATFORMS:
        - ruby
        - x86_64-darwin-12
      - GEM PATHS:
         - /Users/ttm/.rbenv/versions/2.0.0-p247/lib/ruby/gems/2.0.0
         - /Users/ttm/.gem/ruby/2.0.0
      - GEM CONFIGURATION:
         - :update_sources => true
         - :verbose => true     
         - :backtrace => false
         - :bulk_threshold => 1000
      - REMOTE SOURCES:
         - https://rubygems.org/
      - SHELL PATH:
         - /Users/ttm/.rbenv/versions/2.0.0-p247/bin
         - /Users/ttm/.rbenv/libexec
         - /Users/ttm/.rbenv/plugins/ruby-build/bin
         - /Users/ttm/perl5/perlbrew/bin
         - /Users/ttm/perl5/perlbrew/perls/perl-5.18.1/bin
         - /Users/ttm/.pyenv/shims
         - /Users/ttm/.pyenv/bin
         - /Users/ttm/.rbenv/shims
         - /Users/ttm/.rbenv/bin
         - /Users/ttm/bin
         - /usr/local/mysql-5.6.12-osx10.7-x86_64/bin
         - /Users/ttm/libsmi/bin
         - /usr/local/bin
         - /usr/bin
         - /bin
         - /usr/sbin
         - /sbin
         - /usr/local/bin
#### gem fetch
#### gem generate_index
#### gem help
#### gem install
#### gem list
#### gem lock
#### gem mirror
#### gem open
#### gem outdated
#### gem owner
#### gem pristine
#### gem push
#### gem query
#### gem rdoc
#### gem search
#### gem server
#### gem sources
#### gem specification
#### gem stale
#### gem uninstall
#### gem unpack
#### gem update
#### gem which
#### gem yank

