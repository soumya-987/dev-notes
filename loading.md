# problem
the state would get changed at weird times
# cause
npm works with faster speed and firebase with slower speed
# fix
used 2 state variables one for user( set to null) and one for loading(set to true) and then by using useEffect, extracted the user if user was there loading was set to false and if not then loading would remain true [loading stops the server for a while until the user value is extracted]
# code
function App() {
  const [user,setuser]=useState(null);
  const [loading,setloading]=useState(true);
  useEffect(()=>{
    const unsubscribe =onAuthStateChanged(auth,(currentUser)=>{
      setuser(currentUser);
      setloading(false);
    });
    return () => unsubscribe();
  },);
  if (loading){ return <div>Loading Sephora...</div>}