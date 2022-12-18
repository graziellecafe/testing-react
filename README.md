# Testing React with Jest and React Testing Library
*Code without tests is bad code - Michael Feathers*

This repository was created to learn about test in React using Jest and React Testing Library. 

## Introduction
In particular, tests are divided into three groups. 

- **Unit tests**  automatically check small parts of a piece of code, usually just one class. They form the base of the pyramid, i.e. most tests are in this category. Unit tests are simple, easier to implement and run quickly. 

- **Integration tests** or **service tests**, which check a complete functionality or transaction of a system. So these are tests that use several classes, from different packages, and may also test external components, such as databases. Integration tests require more effort to implement and run more slowly. 

- **System tests**, also called **user interface tests** simulate, as faithfully as possible, a system usage session by a real user. Since they are end-to-end tests, they are more expensive, slower, and less numerous. Interface tests are also usually fragile, that is, minimal changes to the interface components may require modifications to these tests.

## Project 1: Color Button
### Overview 
- Changing button color, disabling button with checkbox 
- Introduce: testing interactions that affect DOM, unit testing functions

### Testing component
#### React code
```javascript
function App() {
  const [buttonColor, setButtonColor] = useState('red'); 
  const newButtonColor = buttonColor === 'red' ? 'blue' : 'red'; 

  return (
    <div>
      <button 
        style = {{ backgroundColor: buttonColor }}
        onClick = {() => setButtonColor(newButtonColor)}>
          Change to {newButtonColor}
      </button>
    </div>
  );
}

export default App;
```
#### Test code
```javascript
import { render, screen, fireEvent } from '@testing-library/react';
import App from './App';

import { render, screen, fireEvent } from '@testing-library/react';
import App from './App';

test('button has correct initial color and text', () => {
  render(<App />); 
  const colorButton = screen.getByRole('button', { name: 'Change to blue' }); 
  expect(colorButton).toHaveStyle({ backgroundColor: 'red' }); 
});
```

## Project 2: Ice-cream sundae 
### Overview 
- Testing more complex user interactions, interactions between components 
- Mocking server responses with Mock Service Worker 
- Testing async functionality 