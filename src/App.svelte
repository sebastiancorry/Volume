<script>
	// External imports.
	// JS.
	import * as showdown from "showdown";

	// Value updated by the input pane.
	let value = "";

	// Markdown to html.
	const converter = new showdown.Converter();
	function markdown_to_html(markdown) {
		return converter.makeHtml(markdown);
	}
</script>


<main>
	<!-- Input pane. -->
	<textarea bind:value={value} rows="100" cols="100"></textarea>
	
	<!-- Display pane. -->
	<div class="display">
		<p>
			{@html markdown_to_html(value)}
		</p>
	</div>
</main>


<style>
	main {
		max-width: 240px;
		margin: 0 auto;
		font-size: 1em;
	}

	textarea {
		width: 47%;
		height: 100%;
		resize: none;
		position: absolute;
		top: 0;
		left: 1%;
		background-color: #383F51;
		color: #FFFFF0;
	}

	p {
		font-family: Monaco, monospace;
	}

	.display {
		position: absolute;
		top: 0;
		right: 1%;
		width: 47%;
		height: 100%;
		overflow: auto;
	}

	:global(body) {
		background-color: #383F51;
		color: #FFFFF0;
	}
</style>
