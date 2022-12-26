1- To track error in the console is very useful to add the devtool: 'inline-source-map' line to the webpack.config.js file, of this way we can track which as the file with the issue nad what line.
2- To avoid run the build command every time we do a change is very useful install webpack-dev-server:
npm install --save-dev webpack-dev-server
We also need to add the above line to webpack.config.js:
  devServer: {
    static: './dist',
  },
  optimization: {
    runtimeChunk: 'single',  //The optimization.runtimeChunk: 'single' was added because in this example we have more than one entrypoint on a single HTML page. Without this, we could get into trouble described here. Read the Code Splitting chapter for more details.
  },

  command => "start": "webpack serve --open",