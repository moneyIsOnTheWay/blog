---
title: springboot切面操作的重定向
date: 2017-12-24 17:02:05
tags: framework
categories: Java
---
## SpringBoot Aspect中的重定向

*登录拦截*

    @Aspect
    @Component
    public class HttpAspect {
        @Autowired
        private HttpServletRequest httpServletRequest;
    
        @Pointcut("execution(public * com.wy.centosafe.controller.PageController.*(..)))")
        public void check(){
        }
    
        @Around("check()")
        public String doBefore(ProceedingJoinPoint pjo){
            HttpSession session = httpServletRequest.getSession();
            if(session.getAttribute("name") == null){
                return "redirect:/forbidden";
            }else {
                return null;
            }
        }
    }
