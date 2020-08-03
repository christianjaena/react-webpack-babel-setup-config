1. mkdir public src
2. touch public/index.html src/index.js
3. npm init -y
4. npm install webpack webpack-cli -D
5. npm install react react-dom
6. touch webpack.config.js at root
7. set entry and output for bundle.js at public/index.html
8. put div with root id in html and import script './bundle.js'
9. test React app in index.js w/o JSX i.e. createElement because there's no babel yet to transpile jsx
10. modify scripts at package.json to { start: "webpack --mode=development", build: "webpack --mode=production" }
11. run by npm start and open browser manually and test if it works
12. npm i @babel/core @babel/preset-env @babel/preset-react babel-loader -D 
13. create .babelrc at root folder and set preset: ["@babel/preset-env", "@babel/preset-react"]
14. add module to webpack 
	module: {
		rules: [
			{
				test: /\.jsx$/,
				exclude: /node_modules/,
				loader: 'babel-loader'
			}
		]
	}
15. add devtool to webpack devtool: 'cheap-module-eval-source-map'
16. test react app w/ JSX
17. npm i webpack-dev-server -D
18. add config to webpack 
	devServer: {
		contentBase: path.join(__dirname, 'public')
	}
19. add to scripts "dev": "webpack-dev-server" and test run npm run dev
20. npm i css-loader style-loader -D 
21. add to rules for CSS
 {
	 test: /\.css$/,
	 use: ['style-loader', 'css-loader']
 }

 22. npm i sass-loader node-sass -D
 23. add to rules for SCSS
 {
	 test: /\.scss$/,
	 use ['style-loader', 'css-loader', 'sass-loader']
 }
 
