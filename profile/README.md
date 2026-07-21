<h1 align="center">CROWN</h1>

<p align="center">
  Донаты автору без посредника между кошельком донора и получателем.<br>
  Деньги идут ончейн. Мы их не держим и не можем остановить.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Solana-devnet-7C3AED?style=flat-square" alt="Solana devnet">
  <img src="https://img.shields.io/badge/Internet_Computer-canisters-7C3AED?style=flat-square" alt="ICP">
  <img src="https://img.shields.io/badge/Rust-ядро-7C3AED?style=flat-square" alt="Rust">
</p>

---

## Как это работает

```
донор ──▶ сплиттер (Solana)  ──▶ получатель
              │                  комиссии нет, баланса нет
              ▼
        crown-index (ICP)
        открытая книга репутации
              │
              ▼
        Crown App — профиль, цели, OBS-оверлей
```

Три вещи, которые стоит понять сразу:

1. **Сплиттер неизменяемый.** У него нет владельца, нет комиссии и нет баланса — деньги проходят насквозь.
2. **Книга репутации открыта.** Кто сколько задонатил, видно всем и проверяется независимо.
3. **Фронтенд ничего не решает.** Он вне доверенного контура: ни денег, ни ключей. Упадёт сайт — платежи продолжат работать.

## Репозитории

### Ядро

| | |
|---|---|
| **[Crown-Core](https://github.com/Crown-protocol/Crown-Core)** | Сплиттер на Solana + канистра `crown-index`, сворачивающая сеттлменты в книгу репутации |
| **[Crown-Factory](https://github.com/Crown-protocol/Crown-Factory)** | Эскроу-фабрики формы `two-outcome` и `crown-derive` — атрибуция сеттлмента донору через PDA |

### Приложение

| | |
|---|---|
| **[Crown-App](https://github.com/Crown-protocol/Crown-App)** | Сайт, личный кабинет, кампании, мини-игры, OBS-оверлеи. Next.js 14 |

### Crown Games

Резолверы на ICP поверх форм из `Crown-Factory`. Ни один не держит денег и не шлёт транзакций — только читает цепь и подписывает исход.

| | |
|---|---|
| **[Conditional-Tasks](https://github.com/Crown-protocol/Conditional-Tasks)** | Условные задания: голосование весом книги, threshold-вердикт |
| **[Conditional-Funding](https://github.com/Crown-protocol/Conditional-Funding)** | Сбор: краудфандинг, один вердикт на коллекцию эскроу |
| **[Auction](https://github.com/Crown-protocol/Auction)** | Аукцион: реестр лотов, ставки читаются с цепи, победитель по цене |
| **[Subscription](https://github.com/Crown-protocol/Subscription)** | Подписка: предоплаченные потоки, `cancel` по подписи донора |

## Стек

**Solana** — расчёты и эскроу, Rust
**Internet Computer** — резолверы и книга репутации, канистры на Rust
**Next.js 14** — фронтенд на TypeScript

## Статус

Devnet. Проект в активной разработке — интерфейсы могут меняться.
