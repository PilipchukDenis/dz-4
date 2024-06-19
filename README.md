<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fined1</title>
    <link rel="stylesheet" href="dz 8 style .css">
    <script src="dz 8.js" defer></script>



</head>

<div class="box">
    <h2>Create new color</h1>
        <form class="form_cont" action="">
            <label for="">Color
                <input type="text" name="" pattern="[A-Za-z]" title="only latin letters not numbers" id="color_name"
                    required minlength="4">
            </label>
            <label for="">Type
                <select name="" id="Type">
                    <option value="RGB">RGB</option>
                    <option value="HEX">HEX</option>
                    <option value="RGBA">RGBA</option>
                </select>
            </label>
            <label for="">Code
                <input type="text" name="" pattern="[A-F#0-9]" title="use 0-9,#,A-F" id="color_code" required
                    minlength="4">
            </label>
            <button class="button" id='save' onclick="add();">SAVE

            </button>
        </form>

</div>
<form id="form">
    <fieldset>
        <legend>Сохранение цвета в cookie</legend>
        <p>
            Выбрать цвета для сохранения: <input onchange="choiceColor(event)" type="color" value="#000000" name=""
                id="" />
        </p>
        <p id="choice">Выбранные цвета:</p>
        <p>
            Сохранить в cookie: <input onclick="saveCookie()" type="button" value="Save" name="" id="" />
        </p>
        <p id="keep">Сохранённые в cookie цвета:</p>
        <p>
            Удалить cookie: <input onclick="delCookie()" type="button" value="Delete" name="" id="" />
        </p>
        <p>document.cookie: <span id="result"></span></p>
    </fieldset>
</form>
</div>




</html>



 <script src="dz 8.js" defer>
let form = document.querySelector('#form'), 
        choice = form.querySelector('#choice'),
        keep = form.querySelector('#keep'),
        result = form.querySelector('#result'),
        
        key = 'colors=',
        reg = /colors=([^;]+)/,
        arr = [];
    
    const insert = (target, str) => {
        let html = '&nbsp;<span style="padding: 0px 10px; background-color: ' + str + ';"></span>';
        target.insertAdjacentHTML('beforeEnd', html);
    };
 
    const choiceColor = e => {
        let target = e.currentTarget;
        arr = [...arr, target.value];
        insert(choice, target.value);
    };
    
    (() => {
        if( !document.cookie.match(reg) ) return;
        let cook = JSON.parse(document.cookie.match(reg)[1]);
        for(let color of cook) insert(keep, color);
        result.innerText = document.cookie;
    })();
    
    const saveCookie = e => {
        if(!arr.length) {
            alert('Цвета для сохранения не выбраны');
            return;
        }
        if( document.cookie.match(reg) ) {
            arr = [...JSON.parse(document.cookie.match(reg)[1]), ...arr];
        }
        document.cookie = key + JSON.stringify(arr);
        location.href = location.href;
    };
    
    const delCookie = e => {
        if( !document.cookie.match(reg) ) return;
        document.cookie = key;
        location.href = location.href;
    };
    </script>