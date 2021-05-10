# No Cognito Identity pool provided for unauthenticated access

Add to index.jsx
```jsx
// AWS amplify modules
import Amplify, { Auth } from 'aws-amplify'
import awsconfig from './aws-exports'
Amplify.configure(awsconfig)
Auth.configure(awsconfig)
```