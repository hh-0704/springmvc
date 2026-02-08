# 🌱 Spring MVC 기본 기능 학습 프로젝트

> 인프런 김영한님의 **스프링 MVC 1편 - 백엔드 웹 개발 핵심 기술** 중 "스프링 MVC - 기본 기능" 챕터 학습 저장소

## 📚 프로젝트 소개

이 프로젝트는 Spring MVC의 핵심 기능을 체계적으로 학습하고 실습한 내용을 담고 있습니다. 
서블릿 기반의 전통적인 방식에서 Spring MVC가 어떻게 개발을 편리하게 만들어주는지 단계별로 학습합니다.

## 🎯 학습 목표

- **로깅**: SLF4J와 Logback을 사용한 실무 로깅 방식 이해
- **요청 매핑**: URL 매핑, HTTP 메서드 매핑, PathVariable 등 다양한 매핑 방법 학습
- **요청 파라미터 처리**: @RequestParam, @ModelAttribute를 활용한 데이터 바인딩
- **HTTP 메시지 처리**: @RequestBody, @ResponseBody, HttpEntity를 통한 JSON 처리
- **HTTP 응답**: 정적 리소스, 뷰 템플릿, HTTP API 응답 방식 이해
- **HTTP 메시지 컨버터**: 스프링 MVC의 내부 동작 원리 파악
- **핸들러 어댑터 구조**: ArgumentResolver, ReturnValueHandler의 역할 이해

## 🛠 기술 스택

- **Java**: 11
- **Spring Boot**: 2.4.x
- **Build Tool**: Gradle
- **Template Engine**: Thymeleaf
- **Logging**: SLF4J + Logback
- **기타**: Lombok

## 📝 학습 노트

### 주요 애노테이션 비교

| 애노테이션 | 용도 | 특징 |
|-----------|------|------|
| `@Controller` | 뷰 반환 | String 반환 시 뷰 이름으로 인식 |
| `@RestController` | HTTP 메시지 바디 반환 | `@ResponseBody` 포함 |
| `@RequestParam` | 쿼리 파라미터, Form 데이터 | 단순 타입에 적용 |
| `@ModelAttribute` | 객체 바인딩 | 요청 파라미터를 객체에 자동 매핑 |
| `@RequestBody` | HTTP 메시지 바디 읽기 | JSON → 객체 변환 |
| `@ResponseBody` | HTTP 메시지 바디 쓰기 | 객체 → JSON 변환 |

### 파라미터 생략 규칙

스프링은 애노테이션 생략 시 다음 규칙을 적용:
- **단순 타입** (`String`, `int`, `Integer` 등) → `@RequestParam`
- **나머지** (사용자 정의 객체 등) → `@ModelAttribute`

⚠️ **주의**: Spring Boot 3.2부터 `-parameters` 컴파일 옵션 필요

### HTTP 메시지 컨버터 선택 기준

1. **요청**: 대상 클래스 타입 + Content-Type
2. **응답**: 대상 클래스 타입 + Accept (또는 `@RequestMapping`의 `produces`)

## 🔗 참고 자료

- [강의 링크](https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81-mvc-1)
- [Spring MVC 공식 문서](https://docs.spring.io/spring-framework/docs/current/reference/html/web.html#mvc)
- [Spring Boot 공식 문서](https://docs.spring.io/spring-boot/docs/current/reference/html/)

---

**강의**: 인프런 - 스프링 MVC 1편 (김영한)
