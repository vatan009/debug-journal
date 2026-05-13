react-dom_client.js?v=cebd2d2f:4254 Uncaught Error: Too many re-renders. React limits the number of renders to prevent an infinite loop.
    at renderWithHooksAgain (react-dom_client.js?v=cebd2d2f:4254:53)
    at renderWithHooks (react-dom_client.js?v=cebd2d2f:4214:62)
    at updateFunctionComponent (react-dom_client.js?v=cebd2d2f:5568:16)
    at beginWork (react-dom_client.js?v=cebd2d2f:6139:20)
    at runWithFiberInDEV (react-dom_client.js?v=cebd2d2f:850:66)
    at performUnitOfWork (react-dom_client.js?v=cebd2d2f:8428:92)
    at workLoopSync (react-dom_client.js?v=cebd2d2f:8324:37)
    at renderRootSync (react-dom_client.js?v=cebd2d2f:8308:6)
    at performWorkOnRoot (react-dom_client.js?v=cebd2d2f:7993:27)
    at performWorkOnRootViaSchedulerTask (react-dom_client.js?v=cebd2d2f:9058:4)


reason :

import React,{useState} from 'react'
export default function Question1() {
  const [count, setCount] = useState(0);

  return (
    <div onClick={setCount((prev)=>prev+1) }>{count}</div>
  )
}

soln :
return <div onClick={() => setCount((prev) => prev + 1)}>
