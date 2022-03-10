<html>
  webchatv2
</html>  
  <script src="https://apps.mypurecloud.com/widgets/9.0/cxbus.min.js" onload="javascript:CXBus.configure({debug:false,pluginsPath:'https://apps.mypurecloud.com/widgets/9.0/plugins/'}); CXBus.loadPlugin('widgets-core');"></script>

<script>
  window._genesys = {
    "widgets": {
      "webchat": {
        "transport": {
          "type": "purecloud-v2-sockets",
          "dataURL": "https://api.mypurecloud.com",
          "deploymentKey": "0577e484-e23f-4abc-86f8-dc3d33ee3dd8",
          "orgGuid": "70c90251-f511-4f03-acbd-14637be1743e",
          "interactionData": {
            "routing": {
              "targetType": "QUEUE",
              "targetAddress": "Travis Blended Queue",
              "priority": 2
            }
          }
        },
        "userData": {
          "addressStreet": "",
          "addressCity": "",
          "addressPostalCode": "",
          "addressState": "",
          "phoneNumber": "",
          "customField1Label": "",
          "customField1": "",
          "customField2Label": "",
          "customField2": "",
          "customField3Label": "",
          "customField3": ""
        }
      }
    }
  };

  function getAdvancedConfig() {
    return {
      "form": {
        "autoSubmit": false,
        "firstname": "",
        "lastname": "",
        "email": "",
        "subject": ""
      },
      "formJSON": {
        "wrapper": "<table></table>",
        "inputs": [
          {
            "id": "cx_webchat_form_firstname",
            "name": "firstname",
            "maxlength": "100",
            "placeholder": "Required",
            "label": "First Name"
          },
          {
            "id": "cx_webchat_form_lastname",
            "name": "lastname",
            "maxlength": "100",
            "placeholder": "Required",
            "label": "Last Name"
          },
          {
            "id": "cx_webchat_form_email",
            "name": "email",
            "maxlength": "100",
            "placeholder": "Optional",
            "label": "Email"
          },
          {
            "id": "cx_webchat_form_subject",
            "name": "subject",
            "maxlength": "100",
            "placeholder": "Optional",
            "label": "Subject"
          }
        ]
      }
    };
  }

  const customPlugin = CXBus.registerPlugin('Custom');
</script>

<button type="button" id="chat-button" onclick="customPlugin.command('WebChat.open', getAdvancedConfig());">Start Chat</button>
