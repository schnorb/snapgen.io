# snapgen.io

# Start of code

<!DOCTYPE html>
<html>
<body style="background:#1E1E1E; color:white; font-family:Arial; padding:20px;">

<h2 style="color:#00A8F0;">Snapchat Generator</h2>

<style>
  input, textarea {
    padding: 8px;
    border-radius: 4px;
    border: none;
    background: #2b2b2b;
    color: white;
  }
  textarea { width: 600px; resize: vertical; }

  #colorPreview {
    width: 25px;
    height: 25px;
    border-radius: 4px;
    border: 1px solid #666;
    display: inline-block;
    vertical-align: middle;
    margin-left: 10px;
  }
</style>

Username:<br>
<input id="u"><br><br>

Message:<br>
<textarea id="m" rows="4"></textarea><br><br>

Colour:<br>
<select id="colorPick"
        style="padding:8px; border-radius:4px; border:none; background:#2b2b2b; color:white;">
  <option value="#00A8F0">Normal Blue</option>
  <option value="#3CA936">Will Green</option>
  <option value="#E50184">Tilly Pink</option>
  <option value="#8936B6">Ainslie Purple</option>
  <option value="#3461EF">Mylene Blue</option>
  <option value="#D80030">Gus Red</option>
</select>

<div id="colorPreview" style="background:#00A8F0;"></div>

<br><br>

<button id="genBtn"
        style="padding:10px 20px; background:#00A8F0; border:none; border-radius:5px; font-weight:bold; cursor:pointer;">
    Generate
</button>

<div id="out" 
     style="margin-top:30px; display:none; font-family:'Helvetica Neue', Arial, sans-serif;">

    <div id="name" 
         style="font-size:13px; font-weight:600; margin-bottom:4px; letter-spacing:0.4px; text-transform:uppercase;">
    </div>

    <div id="borderWrapper" style="border-left:2px solid #00A8F0; padding-left:6px;">
        <div id="msg" 
             style="font-size:15px; font-weight:1000; line-height:1.5; letter-spacing:1px; white-space:pre-wrap;">
        </div>
    </div>

</div>

<script>
// Update preview box when dropdown changes
document.getElementById("colorPick").addEventListener("change", function() {
    document.getElementById("colorPreview").style.background = this.value;
});

// Make Generate button actually run go()
document.getElementById("genBtn").addEventListener("click", go);

// Main generator function
function go() {
    const user  = document.getElementById("u").value || "USERNAME";
    const msg   = document.getElementById("m").value || "your message";
    const color = document.getElementById("colorPick").value || "#00A8F0";

    document.getElementById("name").innerText = user.toUpperCase();
    document.getElementById("name").style.color = color;

    document.getElementById("borderWrapper").style.borderLeft = "2px solid " + color;
    document.getElementById("msg").innerText = msg;

    document.getElementById("out").style.display = "block";
}
</script>

</body>
</html>
