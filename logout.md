# problem 
the sign in screen would not show up and the sign in button would not work
# cause
in the firebase it stores if u have signed in and keeps you signed in 
# fix
importing sign out and auth(tells the function from where to sign out) from firebase then by trying and catching thr error, finally signing out 
# code
   const handleLogout =async ()=>{
        try{
            await signOut(auth);
            alert("Signed out successfully!");
        }catch(error){
            console.error("Error signing out:",error.message);
        }
