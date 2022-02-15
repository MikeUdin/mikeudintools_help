---
description: how to write user scripts for Batch Processor plugin
---

# User Scripts

**Batch Processor** plugin allows you to run a custom script for each document in the queue. with the standard plugin package you can find several scripts that serve as a demonstration of how you can expand plugin functionality with _Cinema 4D Python API_!

Below is an example of a simple script, all the details of its writing are indicated in the comments.

![Example User Script Output](<../.gitbook/assets/image (4).png>)

{% code title=".\res\scripts\Demo_Script.py" %}
```python
import c4d
from c4d import gui

'''
Batch processor User Script Basic Example
Please follow the code comments 
https://mikeudin.net/


To add User Scipt dialog make sure:
1. Your dialog is based on gui.Subdialog class
2. Class must have a name 'UserScriptDialog'
3. Class must have a class variable 'user_script_container' to store all data on it
4. Script must have 'main' function that will be executed by Batch Processor
5. 'user_script_container' from dialog will be used as input argument for 'main' function
6. Forbidden Functions: Perform any GUI functionality. (E.g. displaying messages, opening dialogs etc.)
'''

class UserScriptDialog(gui.SubDialog):
    """
    A SubDialog to display the passed string, its used as example for the actual content of a Tab
    """
    
    STRING_FIELD = 2000
    INT_FIELD = 2001

    # define user_script_container as dictionary
    user_script_container = dict()
    
    def CreateLayout(self):

        # Add your dialog gui elements as descibed on Cinema 4D Python API
        # Please use methods which is compatible with Cinema 4D R19+ Python API
        
        bc = c4d.BaseContainer()
        bc.SetBool(c4d.QUICKTAB_BAR, True)  
        bc.SetString(c4d.QUICKTAB_BARTITLE, 'Script Options')
        self.AddCustomGui(1000, c4d.CUSTOMGUI_QUICKTAB, '', c4d.BFH_SCALEFIT, 0, 0, bc)

        if self.GroupBegin(1001,flags=c4d.BFH_SCALEFIT | c4d.BFV_TOP,cols=2,rows=1,title='Script Options'):
            
            self.GroupSpace(15, 6)
            self.GroupBorderSpace(15,5,15,10)

            self.AddStaticText(1002, c4d.BFH_LEFT, name='My String Data')
            self.AddEditText(self.STRING_FIELD, c4d.BFH_SCALEFIT | c4d.BFV_SCALEFIT, 0, 10)

            self.AddStaticText(1003, c4d.BFH_LEFT, name='My Integer Data')
            self.AddEditNumberArrows(self.INT_FIELD, c4d.BFH_LEFT | c4d.BFV_SCALEFIT, 80, 10)

            self.GroupEnd()

        return True

    def Command(self,id,msg):

        # Assign data to 'user_script_container' variable on any user gui interaction
        if id in {self.STRING_FIELD,self.INT_FIELD}:
            self.user_script_container['int'] = self.GetInt32(self.INT_FIELD)
            self.user_script_container['string'] = self.GetString(self.STRING_FIELD)

        return True

# On execution 'user_script_container' will be used as input argument for 'main' function. 
# if User Scipt do not contains dialog, 'main' function will be executed without arguments.

def main(data):
    
    '''
    Batch Processor adds some global variables to User Script:
    
    doc - referenced to a processed document, type: c4d.BaseDocument
    doc_index - referenced to an document index in Jobs Queue, type: int
    docs_total - total number of documents in a Jobs Queue, type:int

    op - Active Object of processed document, type: c4d.BaseObject 
    mat - Active Material of processed document, type: c4d.Material
    tp - Particle System of processed document, type: c4d.modules.thinkingparticles.TP_MasterSystem

    '''

    # All data that needed to be printed will be passed to plugin Log tab
    print 'Processed Document Index {0} from {1}'.format(doc_index,docs_total) 
    print 'Document name: ', doc.GetDocumentName()
    print 'Document path: ', doc.GetDocumentPath()
    print 'Document Active Object is ', op
    
    print 'My String data', data['string']
    print 'My Integer data', data['int']
    
    if 3 < doc_index < 7:
        # If index of processed document have a number 4,5,6
        # in this case User Scipt will return error   
        raise Exception('Error!')

```
{% endcode %}

