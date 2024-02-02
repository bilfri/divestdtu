<script>
async function fetchOmtale(sub) {
  const URL = `https://api.baserow.io/api/database/rows/table/229023/?user_field_names=true`;
  const headers = { 'Authorization': 'Token W8KFgVEGarJKtrRV328AErZTSVd2cjfw' };
  const fetchResult = fetch(URL, { headers} );
  const response = await fetchResult;
  const jsonData = await response.json();
  return jsonData
}

function makeUL(json) {
    // Create the list element:
    var list = document.createElement('ul');

    for(var i = 0; i < Object.keys(json).length; i++) {
        // Create the list item:
        var item = document.createElement('li');

        // Set its contents:
        item.appendChild(document.createTextNode(Object.values(json)[i]));

        // Add it to the list:
        list.appendChild(item);
    }

    // Finally, return the constructed list:
    return list;
}

// Add the contents of json to #foo:
// document.getElementById('omtaleListe').appendChild(makeUL(json));

const omtaleJSON = await fetchOmtale('javascript');

const omtaleArray = omtaleJSON["results"];

console.log(omtaleArray[0]);
</script>