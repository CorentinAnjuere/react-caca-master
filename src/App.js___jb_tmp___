import React, {Component} from 'react';
import logo from './logo.svg';
import './App.css';

class App extends React.Component {
    constructor() {
        super();
        this.state = {
            seriesList: [],
            seriesEpisodesList: [],
            value:''
        }
        this.handleChange = this.handleChange.bind(this);
    }

    handleChange(event) {
        this.setState({value: event.target.value});
    }

    componentDidMount() {

        fetch('seriesList.json',{})
            .then(response => response.json())
            .then(seriesListDepuisFichier => {
                this.setState({seriesList: seriesListDepuisFichier});

            })
            .catch(function (error) {
                console.log(error);
            })
            .then(function () {
                alert("j'ai fait ce que j'ai pu");
            });

    }

    render() {
        return (
            <div>
                <ul>
                    {this.state.seriesList.length ?
                        this.state.seriesList.map(item => <li key={item.id}>{item.seriesName}</li>)
                        : <li>Loading...</li>
                    }
                    <input type="text" value={this.state.value} onChange={this.handleChange} />
                    <p>{this.state.value}</p>
                </ul>
            </div>
        )
    }
}


export default App;

