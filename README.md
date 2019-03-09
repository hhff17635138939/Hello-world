# Hello-world
join my home

    /**
	     * 分页查询用户信息
	     * @param pn 默认从第一页开始  请求参数
	     * @param model
	     * @return
	     */
	    @RequestMapping("userInfo")
	    public String getUsers(@RequestParam(value="pn",defaultValue="1")Integer pn,Model model){
	        //从第一条开始 每页查询五条数据
	        PageHelper.startPage(pn, 5);
	        List<User> users = userService.findAll();
	        //将用户信息放入PageInfo对象里
	        PageInfo page = new PageInfo(users,5);
	        model.addAttribute("pageInfo", page);
	        return "allUser"
	    }
