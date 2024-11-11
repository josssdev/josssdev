
  <div align="center">
  <img src="icon.gif" alt="Logo" />
  </div>



<div align="center">

# Jose Gutierrez
### Desarrollador Web y Móvil | Diseñador

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/josssdev)
[![Instagram](https://img.shields.io/badge/Instagram-000000?style=for-the-badge&logo=Instagram&logoColor=red)](https://www.instagram.com/joss_0700/)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=About.me&logoColor=white)](https://josssdev.github.io/Portafolio-Joss.Dev)

</div>

## 👨‍💻 Sobre mí

Soy desarrollador y diseñador con más de 2 años de experiencia creando aplicaciones móviles y páginas web. Me especializo en React, React Native, HTML, CSS, JavaScript y Diseño Grafico. Siempre enfocándome en la experiencia de usuario y el diseño funcional. Me encanta transformar ideas en soluciones digitales simples y efectivas.

## 💼 Experiencia

### Desarrollador Web y Móvil | JossDev
`2022 - Presente`
- Desarrollo de aplicaciones web y móviles
- Implementación de soluciones tecnológicas
- Diseño de interfaces de usuario

### Freelance - Desarrollo Web y Diseño
`2021 - Presente`
- Desarrollo de proyectos personalizados
- Diseño gráfico y web
- Consultoría tecnológica

### Proyectos Personales
`2021 - Actualidad`
- Investigación y desarrollo de nuevas tecnologías
- Creación de contenido técnico
- Contribuciones a proyectos open source

## 🛠 Habilidades

<div align="center">

| Frontend | Backend | Diseño | Herramientas |
|----------|---------|--------|--------------|
| HTML5    | Node.js | Adobe Illustrator | GitHub |
| CSS3     | Express | Adobe Photoshop   | Spark AR |
| React    | API REST| UI/UX Design      | Git |
| React Native | Kotlin | Responsive Design | VS Code |
| Tailwind CSS | JavaScript | Mobile First | Figma |

</div>

## 🚀 Proyectos Destacados

### Med Ally
Plataforma digital que facilita el acceso a información médica confiable.
- React Native
- Node.js
- MongoDB
- [Ver Proyecto →]([https://proyecto1.com](https://josssdev.github.io/MedAlly/))

### Flashcards
Herramienta interactiva para crear, estudiar y compartir tarjetas de estudio personalizables.
- React
- Express
- PostgreSQL
- [Ver Proyecto →](https://josssdev.github.io/Flashcards.joss/)

### Consultorio Medico Familiar Adulam
Centro de salud dedicado al cuidado integral de familias.
- Next.js
- Tailwind CSS
- Strapi CMS
- [Ver Proyecto →]([https://proyecto3.com](https://josssdev.github.io/Adulam/))

### Arepa Colombianas
Tienda en línea de arepas auténticas colombianas.
- React
- Node.js
- Stripe
- [Ver Proyecto →]([https://proyecto4.com](https://josssdev.github.io/Arepas-Colombianas/))

## 📊 Estadísticas de GitHub

<div align="center">

![GitHub stats](https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true&theme=radical)

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact&theme=radical)

</div>

## 📫 Contacto

- 📧 Email: [jossgu2023@gmail.com](jossgu2023@gmail.com)
- 💼 LinkedIn: [Jose Gutierrez](https://linkedin.com/in/yourusername)
- 🌐 Portfolio: [JOSS.DEV](https://josssdev.github.io/Portafolio-Joss.Dev/)

<div align="center">

---

### 💪 "Transformando ideas en código, diseñando el futuro digital"
</div>

🎮 ¡Juguemos!
¿Te apetece un pequeño desafío? Juega una partida de Piedra, Papel o Tijeras contra la computadora:
import React, { useState } from 'react'
import { Scissors, Hand, Square } from 'lucide-react'

export default function Component() {
  const [playerChoice, setPlayerChoice] = useState<string | null>(null)
  const [computerChoice, setComputerChoice] = useState<string | null>(null)
  const [result, setResult] = useState<string | null>(null)

  const choices = ['rock', 'paper', 'scissors']

  const play = (choice: string) => {
    const computerChoice = choices[Math.floor(Math.random() * choices.length)]
    setPlayerChoice(choice)
    setComputerChoice(computerChoice)

    if (choice === computerChoice) {
      setResult('Empate!')
    } else if (
      (choice === 'rock' && computerChoice === 'scissors') ||
      (choice === 'paper' && computerChoice === 'rock') ||
      (choice === 'scissors' && computerChoice === 'paper')
    ) {
      setResult('¡Ganaste!')
    } else {
      setResult('La computadora gana.')
    }
  }

  const getIcon = (choice: string | null) => {
    switch (choice) {
      case 'rock':
        return <Square className="w-8 h-8" />
      case 'paper':
        return <Hand className="w-8 h-8" />
      case 'scissors':
        return <Scissors className="w-8 h-8" />
      default:
        return null
    }
  }

  return (
    <div className="flex flex-col items-center justify-center p-4 bg-gray-100 rounded-lg shadow-md">
      <h2 className="text-2xl font-bold mb-4">Piedra, Papel o Tijeras</h2>
      <div className="flex justify-center space-x-4 mb-4">
        {choices.map((choice) => (
          <button
            key={choice}
            onClick={() => play(choice)}
            className="p-2 bg-white rounded-full shadow-md hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-gray-300"
            aria-label={choice}
          >
            {getIcon(choice)}
          </button>
        ))}
      </div>
      {playerChoice && computerChoice && (
        <div className="text-center">
          <p className="mb-2">
            Tu elección: {getIcon(playerChoice)} vs Computadora: {getIcon(computerChoice)}
          </p>
          <p className="text-xl font-semibold">{result}</p>
        </div>
      )}
    </div>
  )
}
