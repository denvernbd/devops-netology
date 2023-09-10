# Задача 1

Опишите кратко, в чём основное отличие полной (аппаратной) виртуализации, паравиртуализации и
виртуализации на основе ОС.

## Ответ

### аппаратная виртуализация:

устанавливается на сервер (железо)
Гипервизор (виртуализационный слой) полностью эмулирует аппаратное обеспечение, так что каждая
виртуальная машина ведет себя как отдельный физический сервер. Она имеет свою собственную
операционную систему и полный доступ к аппаратным ресурсам сервера.

### паравиртуализация:

Работает и устанавливается на операционную систему.
взаимодействуют с гипервизором для доступа к аппаратным ресурсам. В отличие от полной виртуализации,
где гостевые ОС полностью изолированы друг от друга, в паравиртуализации гостевые ОС могут
обмениваться информацией и использовать общие драйверы для взаимодействия с гипервизором.

### виртуализации на основе ОС:

Работает и устанавливается на операционную систему. контейнеры раздеяют между собой ядро хоста  и
используют общие ресурсы, такие как файловая система и сеть. Контейнеры изолированы друг от друга.

# Задача 2

Выберите один из вариантов использования организации физических серверов в зависимости от условий
использования.

Организация серверов:

физические сервера,
паравиртуализация,
виртуализация уровня ОС.
Условия использования:

высоконагруженная база данных, чувствительная к отказу;
различные web-приложения;
Windows-системы для использования бухгалтерским отделом;
системы, выполняющие высокопроизводительные расчёты на GPU.
Опишите, почему вы выбрали к каждому целевому использованию такую организацию.

## Ответ

- Высоконагруженная база данных, чувствительная к отказу:
для максимальной производительности и надёжности предлагаю использовать физические сервера. это
позволит максимально оптимизировать ОС под требования базы данных. Это также обеспечит изоляцию и
предотвращает влияние других приложений на работу базы данных. физические сервера более надёжны
нежели ВМ или Контейнеры.

- Различные web-приложения:
предлагаю использовать виртуализацию уровня ОС.
Это позволит нам запускать несколько изолированных контейнеров на одном физическом сервере,
обеспечивают высокую плотность размещения приложений и эффективное использование ресурсов сервера.
Кроме того, контейнеры могут быстро масштабироваться и управляться, что особенно полезно для
развертывания и масштабирования web-приложений.

- Windows-системы для использования бухгалтерским отделом: тут предлагаю использовать
паравиртуализацию. где мы запустим несколько гостевых операционных систем на одном физическом
сервере. используя Windows-систем, паравиртуализация позволит эффективно использовать ресурсы
сервера и обеспечивает хорошую изоляцию между различными системами.

- Системы, выполняющие высокопроизводительные расчёты на GPU: Физические
сервера обеспечивают прямой доступ к аппаратным ресурсам, включая GPU, что позволяет максимально
использовать их производительность. альтернативные виды виртуализации внесут накладную нагрузку и
ограничения на доступ к аппаратным ресурсам, что может негативно сказаться на производительности

# Задача 3

Выберите подходящую систему управления виртуализацией для предложенного сценария. Детально опишите
ваш выбор.

Сценарии:

100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований. Преимущественно
Windows based-инфраструктура, требуется реализация программных балансировщиков нагрузки, репликации
данных и автоматизированного механизма создания резервных копий.
Требуется наиболее производительное бесплатное open source-решение для виртуализации небольшой
(20-30 серверов) инфраструктуры на базе Linux и Windows виртуальных машин.
Необходимо бесплатное, максимально совместимое и производительное решение для виртуализации
Windows-инфраструктуры.
Необходимо рабочее окружение для тестирования программного продукта на нескольких дистрибутивах
Linux.

## Ответ

- 100 виртуальных машин на базе Linux и Windows, общие задачи, нет особых требований:
В предложенном сценарии использовад бы VMware vSphere. VMware
vSphere является одним из наиболее популярных и широко используемых решений для виртуализации. Он
обеспечивает высокую производительность, надежность и масштабируемость, а также поддерживает как
Linux, так и Windows виртуальные машины. VMware vSphere также предоставляет возможности программного
балансирования нагрузки, репликации данных и создания резервных копий. а так же предлагает
техническую поддержку.

- Виртуализация небольшой инфраструктуры на базе Linux и Windows виртуальных машин: Для
виртуализации небольшой инфраструктуры на базе Linux и Windows виртуальных машин можно рассмотреть
использование Proxmox VE или oVirt.

- Бесплатное решение для виртуализации Windows-инфраструктуры: Для виртуализации
Windows-инфраструктуры можно рассмотреть использование Microsoft Hyper-V Server. Microsoft Hyper-V
специально оптимизировано для работы с Windows-средой. Оно обеспечивает высокую производительность
и совместимость с Windows виртуальными машинами.

# Задача 4

Опишите возможные проблемы и недостатки гетерогенной среды виртуализации (использования нескольких
систем управления виртуализацией одновременно) и что необходимо сделать для минимизации этих рисков
и проблем. Если бы у вас был выбор, создавали бы вы гетерогенную среду или нет? Мотивируйте ваш
ответ примерами.

## Ответ

Гетерогенная среда потребует индивитуальный подход к каждому компоненту. индивидуальный подход
потребует повышения требования к обслуживающему персоналу тк необходимы знания нескольких платформ,
 особенно если системы управления имеют разные концепции и подходы. Столкнемся с проблемами
совместимости и интеграции между разлиными компонентами среды. В гетерогенной среде
увеличивается сложность обеспечения отказоустойчивости и резервного копирования. Разные системы
управления могут иметь разные механизмы репликации данных, создания резервных копий и
восстановления.

Для минимизации рисков необходима стандартизация и автоматизация процессов управления гетерогенной
средой. Так же разработка общей стратегии отказоустойчивости и резервного копирования для
может помочь упростить процессы восстановления и обеспечить надежность работы всей среды.

Наличие гетерогенной среды диктуется условиями использования. если разрабатываемый продукт требует
адаптации под различные виды платформ виртуализации то без гетерогенной среды не обойтись, так
наличие финансовых ресурсов может повлиять на выбор среды для построения. Важно провести анализ
затрат, сложности управления и интеграции, а также оценить, насколько важна гибкость и совместимость
различных систем в предполагаемых условиях работы.

