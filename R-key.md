react.development.js:199 Warning: Each child in a list should have a unique "key" prop.

Check the render method of `NoteEditor`. See https://reactjs.org/link/warning-keys for more information.
    at div
    at NoteEditor (eval at <anonymous> (about:srcdoc:31:9), <anonymous>:27:29)

function reducer(state, action) {
  switch (action.type) {
    case "ADD":
      return { notes: [...state.notes, { id: Date.now(), text: action.text }] };
    case "EDIT":
      return { notes:[state.notes.map((e)=>{
        if (e.id===action.id){
          return {...e,text:action.text}
        }
        return e;
      })] };
    default:
      return state;
  }

fix :{state.notes.map((note) => (
   <div>
      ...
   </div>
))}
{state.notes.map((note) => (
   <div key={note.id}>
      ...
   </div>
))}
