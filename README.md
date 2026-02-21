# repostat

Простой и легковесный React-компонент для отображения карточки с основной информацией о репозитории GitHub. 

Идеально подходит для дашбордов, портфолио или блогов, где нужно быстро показать статистику проекта (звезды, форки, описание).

## Установка

Вы можете установить пакет с помощью npm или yarn:

```bash
npm install repostat
# или
yarn add repostat

```

*Примечание: Пакет требует установленных `react` и `react-dom` версии 16.8 или выше.*

## Использование

Для работы компонента вам понадобится [GitHub Personal Access Token (PAT)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token), чтобы избежать лимитов API GitHub.

```tsx
import React from 'react';
import { RepoCard } from 'repostat';

function App() {
  return (
    <div style={{ padding: '20px' }}>
      <h2>Мой проект:</h2>
      
      {/* Пример использования компонента */}
      <RepoCard 
        repo="facebook/react" 
        token="ghp_vAshD...ВАШ_ТОКЕН...12345" 
        username="my-username" 
      />
    </div>
  );
}

export default App;

```

## API / Свойства (Props)

| Свойство | Тип | Обязательное | Описание |
| --- | --- | --- | --- |
| `repo` | `string` | ✅ Да | Полный путь к репозиторию в формате `владелец/имя_репозитория` (например, `facebook/react`). |
| `token` | `string` | ✅ Да | Ваш личный токен доступа GitHub (Personal Access Token) для авторизации запросов. |
| `username` | `string` | ❌ Нет | Имя пользователя GitHub (для дополнительного контекста или аналитики). |

## Особенности

* 📦 Написано на TypeScript (типы включены из коробки).
* 🪶 Без лишних зависимостей (только React).
* 🎨 Простой встроенный дизайн, который не сломает вашу верстку.
* ⚡ Асинхронная загрузка данных прямо из GitHub API v3.