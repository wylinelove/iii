# iii
学习学习iii
 form.on('submit(add)', function(data){
                         console.log(data);
					   var categoryname=$("#categoryname").val();
					   var categoryid=$("#categoryid").val();
					   var method = $(data.elem).find("input:add").html("data-id");
                        // alert(id);
					   console.log(id)
          			//alert(deptname);
					$.ajax({
						type: 'get',
						url:getPath()+'/house/reg',
						data:{
							title:categoryname,
							field:'0',
							id:categoryid
							// id 分类编号
                            // title 分类名称
                            // field 上级分类编号
						},
						dataType: "json",
						success:function(data){
							console.log('data',data)
							if(data.code==200){
								layer.alert("增加成功", {icon: 6},function () {
									var index = parent.layer.getFrameIndex(window.name);
									parent.layer.close(index);
									parent.location.reload();
								 });
							}else{
								layer.msg(data.msg)
							}
							},
							error:function (data){
								console.log(data)
							},
					} );
