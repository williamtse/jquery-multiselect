$.fn.extend({
    multiSelect:function(config){
    	$(this).css({"position":"relative"});
        var input = '<input class="multi-input" type="text" style="height:1.5em;width:100px" placeholder="请选择">';
        var selections = '<ul style="position:absolute;top:1.5em;left:0;list-style:none;padding-left:5px;min-width:100px;display:none;backgroud:white;z-index:99;border:1px solid #ddd;">';
        var field=config.field===undefined?'id':config.field;
        var label=config.label===undefined?'name':config.label;
        var checkeds = config.checkeds!==undefined?config.checkeds:[];
        var options = config.options();
        $.each(options,function(i,v){
        	selections+='<li><label style="display:block;width:100%;border-bottom:1px dotted #ddd"><input type="checkbox" value="'+v[field]+'">'+v[label]+'</label></li>';
        });
        selections+='<li><button style="width:100%;" class="multi-save">确定</button></li>';
        selections+='</ul>';
        $(this).html(input+selections);

		var box= $(this);

		if(config.onInit!==undefined){
			config.onInit(box);
		}

        var boxInput = box.find('.multi-input'),
        	saveBtn = box.find('.multi-save'),
        	optionUl = box.find('ul');

        boxInput.click(function(){
        	optionUl.toggle();
        });

        if(checkeds.length>0){
			boxInput.val('选中'+checkeds.length+'个');
			$.each(optionUl.find('input'),function(idx,input){
				if($.inArray(parseInt($(input).val()),checkeds)){
					$(input).prop('checked',true);
				}
			});
        }

        saveBtn.click(function(){
        	var checkeds = optionUl.find('input:checked');
        	var checkCount = checkeds.length;
        	if(checkCount>0){
        		boxInput.val("选中"+checkCount+"个");
        		config.onSave(box,checkeds);
        	}
        	optionUl.hide();
        });
    }
});
