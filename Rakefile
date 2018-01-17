task :build do
	system "xsltproc --stringparam base.dir ./docs ./tools/xsl/xhtml5/chunk.xsl ./XML/LRG.xml"
end
task :rename do
	Dir.glob(File.join(".", "docs", "*.xhtml")).each{ |f| FileUtils.mv(f, File.join(File.dirname(f), "#{File.basename(f,".xhtml")}.html")) }
end
task :fixLinks do
	Dir.glob(File.join(".", "docs", "*.html")).each do |file|
		lines = IO.read(file).gsub(/\.xhtml/, '.html')
		File.open(file, 'w') do |fp|
			fp.puts lines
		end
	end
end

task :default => [:build, :rename, :fixLinks]