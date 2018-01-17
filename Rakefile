task :default do
	system "xsltproc --stringparam base.dir ./docs ./tools/xsl/xhtml5/chunk.xsl ./XML/LRG.xml"
	Dir.glob(File.join(".", "docs", "*.xhtml")).each{ |f| FileUtils.mv(f, File.join(File.dirname(f), "#{File.basename(f,".xhtml")}.html")) }
end
