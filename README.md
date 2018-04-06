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
