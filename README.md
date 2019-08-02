# ios-Heart-Like-Button
import React from 'react';
import { StyleSheet, View, Text, TouchableHighlight, Image } from 'react-native';

export default class LikeButton extends React.Component{
	state = {
			liked: false,
		};

	handleLikeButton = () => {
		this.setState({
			liked: !this.state.liked,
		});
	}

	render() {
		const likedStyle = this.state.liked ? styles.Liked : undefined;
		const heart = require('./images/heart.png');

		

		return (
				<View style = {styles.container}>
				<TouchableHighlight
					onPress = {this.handleLikeButton}
					underlayColor = 'white'>

					<Image source = {heart} style = {[styles.icon, likedStyle]}/>
				</TouchableHighlight>
				<Text style = {styles.text}> Click to like the Page </Text>
			</View>
		);
	}
}



const styles = StyleSheet.create({
	container: {
		alignItems: 'center',
		marginTop: 100,
	},
	Liked: {
		tintColor: 'red',
	},
	text: {
		fontSize: 20,
	},
	icon: {
		height: 150,
		width: 150,
		tintColor: '#f1f1f1',
	},
});
