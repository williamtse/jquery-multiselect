# jquery-multiselect
jquery dropdown multiselection

## usage


    $(function(){
      $('.multi-select').multiSelect({
        field:'id',
        label:'name',
        options:function(){
          return [
            {name:'A',id:1},
            {name:'B',id:2}
          ];
        },
        checkeds:[1],
        onSave:function(e,checkeds){
          var cks = [];
          $.each(checkeds,function(i,v){
            cks.push($(v).val());
          });
          console.log(cks);
        }
      });
    });

![demo](http://img.hb.aicdn.com/cd67d003b0aea312fe98b1da20aadf27942a1e036f1-CGrpyd_fw658)
