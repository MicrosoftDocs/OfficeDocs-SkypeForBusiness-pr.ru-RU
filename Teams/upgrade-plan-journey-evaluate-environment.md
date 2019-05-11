---
title: Обновление групп Майкрософт | Оценка среды, вопросы обнаружения
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Используйте данное руководство для ознакомьтесь с требованиями для оценки текущей среды для обновления до группами должным образом.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 810daf5f63cc5c1e22bb8ed6d6a110621200c047
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895920"
---
![Этапы обновления пути с акцентом на стадии технической готовности] (media/upgrade-banner-tech-readiness.png "Этапы обновления пути с акцентом на стадии технической готовности")

В этой статье является частью технической готовности этапа обновления пути, действия, которые выполнить параллельно с рабочей области готовность пользователей. Прежде чем продолжить, убедитесь, что вы выполните эти действия из предыдущих этапов:

- [Прикреплено другие заинтересованные стороны проекта](upgrade-enlist-stakeholders.md)
- [Определенные области проекта](https://aka.ms/SkypetoTeams-Scope)
- [Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбранные обновления пути](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Оценка среды перед обновлением до группы

В этой статье дается обзор требований к должным образом оценка текущей среды для работы групп. Оценка среды, определение рисков и требования, которые влияют на общую развертывания. С учетом этих элементов заранее, можно скорректировать планирования для достижения успеха.

## <a name="introduction-to-the-discovery-questionnaire"></a>Общие сведения о анкеты обнаружения

Для достижения результатов целевые ключевые (OKRs), сделанные ранее решения основные службы. Следующим шагом является для обнаружения окружающей среды для оценки все аспекты, связанные с инфраструктуры ИТ, сеть и операции, чтобы убедиться в том, что ваша организация готова для реализации решения. Обнаружение — это один из очень во-первых, ключевые действия, которые предпринять при планировании для поездке группам. Окружающей среды обнаружения должны включать оценку готовности сети чтобы убедиться, что сети могут поддерживает обновление для группы. Выполнение подробного обнаружения среды, чтобы лучше понять текущего состояния и Показать возникли проблемы или — еще более важна — возможные препятствием для выполнения процесса развертывания групп.

Определите риски, связанные с технической как часть окружающей среды оценки и внедрения оценки готовности и разработать план по устранению рисков для каждого определенного риска. Следует включить эту информацию в регистре риска.

Все вопросы, связанные с вашей существующей инфраструктуре совместной работы и клиента Office 365, сети, конечные точки, операций и внедрения и проверки готовности к являются частью анкеты обнаружения окружающей среды. Анкеты делится на несколько разделов, чтобы подтвердить готовность своей организации для развертывания группы в несколько основных областей. Работа с рабочую группу проекта запрошенные сведения с подробности минимально необходимое для облегчения планирования действий.

> [!TIP]
> Можно начать, скопировав анкеты в документе Microsoft Word. Попробуйте ответить на все вопросы и записать все сведения, при перемещении по.

## <a name="project-team"></a>Группы проекта

Убедитесь, что мероприятиям нужных людей для группы проекта. Проверка действия, используемые в [Enlist stakekholders вашего проекта](upgrade-enlist-stakeholders.md).

## <a name="office-365-tenant-details"></a>Сведения о клиента Office 365

Мы настоятельно рекомендуем, что у вас есть active клиента Office 365 при работе с этой анкеты. Еще не активирован или еще не настроен клиента Office 365, в статье [Планирование настройки Office 365 для бизнеса](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Используйте следующую таблицу для записи сведений о клиента Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Обратите внимание, клиент рабочей Office 365 <br>имя и идентификатор в столбце ответов <br/>Если имеется более одного клиента <br>связанный с вашей организации <br>Обратите внимание, все идентификаторы. | Имя клиента: <br/>Идентификатор клиента:| |
> | Какие регионов развернуты клиенты?| | |
> | Являются этих клиентов Office 365 сред или <br>Выделенные? | <input type="checkbox">Сред<br/> <input type="checkbox">Выделенные | |
> | Какие продукты Microsoft Online вы используете сейчас? <br/>Обратите внимание на число пользователей, включенных в каждый <br>службы в столбце примечания. | <input type="checkbox">Группами Майкрософт <br/> <input type="checkbox">Скайп для бизнеса <br>&nbsp; &nbsp; &nbsp;В Интернете <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive для бизнеса <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Другие| |
> | К какому уровню лицензии включен для Скайп для <br>Бизнес-пользователи Online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 <br/> <input type="checkbox">Автономный | Число пользователей <br>для каждого SKU: |
> | Что такое текущего леса Active Directory <br>функциональный уровень в среде? <br/>При наличии более одного леса, запишите подробные сведения <br>в столбце примечания. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 г. <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Что вы используете для каталога <br>Синхронизация сегодня? |<input type="checkbox">Без синхронизации (только облако) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Подключения <br/> <input type="checkbox">Другие (указание в <br>&nbsp;&nbsp; &nbsp;Столбца комментарии.)| |
> | Развернуто ли сейчас федеративное удостоверение <br/>(Служб федерации active Directory или <br>сторонних производителей) | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Если вы используете федеративных удостоверений, что такое <br>Инфраструктура федерации? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Службы федерации Active Directory Windows 2012 г. <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Федерация сторонних производителей <br>&nbsp;&nbsp; &nbsp;шлюза <br>&nbsp;&nbsp; &nbsp;(Обратите внимание на то подробных сведений в <br>&nbsp;&nbsp; &nbsp;Столбца комментарии.) | |
> | Если в настоящее время Ведение active Office 365 <br>клиентов, — это SMTP или SIP-домена из вашего <br>конечных пользователей, связанных с клиента? | <input type="checkbox">Н/д – нет Office 365 <br>&nbsp;&nbsp; &nbsp;клиента на месте <br/> <input type="checkbox">Нет, пользователей SMTP или SIP <br>&nbsp;&nbsp; &nbsp;домена, не сопоставленный <br>&nbsp;&nbsp; &nbsp;с любого клиентами в <br>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Да, пользователей SMTP или SIP <br>&nbsp;&nbsp; &nbsp;связан домена <br>&nbsp;&nbsp; &nbsp;с существующего клиента <br>&nbsp;&nbsp; &nbsp;в Office 365 | |
> | UPN пользователя соответствует основной SMTP-адрес? | <input type="checkbox">Да <br/> <input type="checkbox">Нет <br/> <input type="checkbox">Несогласованно | |

## <a name="existing-collaboration-platform-summary"></a>Существующие сводки платформу совместной работы

Используйте следующую таблицу для записи сведений о существующего развертывания платформу совместной работы.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Развернута ли система Microsoft Teams? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Развернута ли система Skype для бизнеса? <br/>Для локального и гибридного развертываний, убедитесь, что <br>Обратите внимание, версии и накопительным пакетом обновления (CU) <br>сведения в столбце примечания. | <input type="checkbox">Да, Office 365 <br/> <input type="checkbox">Да, гибридное (с Office 365) <br/> <input type="checkbox">Да, локальные <br/> <input type="checkbox">Да, через Интернет, выделенного <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Да, размещенная среда, выделенные <br>&nbsp;&nbsp; &nbsp;(третья сторона) <br/> <input type="checkbox">Да, размещенной на серверах общих (третья сторона) <br/> <input type="checkbox">Нет, другие | |
> | Развернута ли система Microsoft Exchange? <br/>Для локального и гибридного развертываний, убедитесь, что <br>Обратите внимание, версии и текущую подробных сведений в комментарии <br>столбец. | <input type="checkbox">Да, Office 365 <br/> <input type="checkbox">Да, гибридное (с Office 365) <br/> <input type="checkbox">Да, локальные <br/> <input type="checkbox">Да, через Интернет, выделенного <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Да, размещенная среда, выделенные <br>&nbsp;&nbsp; &nbsp;(третья сторона) <br/> <input type="checkbox">Да, размещенная среда, общих <br>&nbsp;&nbsp; &nbsp;(третья сторона) <br/> <input type="checkbox">Нет, другие | |
> | Развернута ли система SharePoint? <br/>Для локального и гибридного развертываний, убедитесь, что <br>Обратите внимание, версии и текущую подробных сведений в комментарии <br>столбец. | <input type="checkbox">Да, Office 365 <br/> <input type="checkbox">Да, гибридное (с Office 365) <br/> <input type="checkbox">Да, локальные <br/> <input type="checkbox">Да, через Интернет, выделенного <br>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox">Да, размещенная среда, выделенные <br>&nbsp;&nbsp; &nbsp;(третья сторона) <br/> <input type="checkbox">Да, размещенная среда, общих <br>&nbsp;&nbsp; &nbsp;(третья сторона) <br/> <input type="checkbox">Нет, другие | |
> | Такое Office 365 OneDrive для бизнеса развертывания? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | У вас есть другой платформы сторонних производителей развернут <br>и сегодня используется? Если это так, обратите внимание на число пользователей <br>Эти платформы и сведений об использовании в комментариях <br>столбец. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Временной резерв <br/> <input type="checkbox">Другие (указать в комментариях <br>&nbsp;&nbsp; &nbsp;столбца.) | Число пользователей: <br/>Сведения о:|
> | Если планируется переместить пользователей из этих сторонних производителей <br>Платформа для групп? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Что такое текущее решение телефонии и конференций <br>пользователей, которые находятся в области действия этой инициативы? | | |
> | Требуется ли [их изготовителей, которые поддерживают прямой маршрутизации](direct-routing-plan.md#supported-session-border-controllers-sbcs) развернуты для вашего офисов, которые находятся в области действия этой инициативы? <br>Если Да, запишите подробные сведения в столбце примечания.| <input type="checkbox">Да <br/> <input type="checkbox">Нет ||

## <a name="collaboration-platform-deployment-details"></a>Сведения о развертывании платформу совместной работы

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (при наличии)

Если это возможно, запись дополнительных сведений о развертывании группы с помощью образца таблицы ниже. Если еще не развернут групп, перейдите в этом разделе.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каким группам пользователей доступна система Teams? | <input type="checkbox">Все пользователи в организации <br/> <input type="checkbox">Конкретных пользователей/групп пользователей <br>&nbsp;&nbsp; &nbsp;(Укажите в столбце примечания) ||
> | Какие функции группами и модальности используются? | <input type="checkbox">На основе канала бесед <br/> <input type="checkbox">Частной беседы <br/> <input type="checkbox">Доступ в качестве гостя <br/> <input type="checkbox">Канал собраний <br/> <input type="checkbox">Закрытый собраний <br/> <input type="checkbox">Закрытый вызова <br/> <input type="checkbox">Динамическая сеть канала meetup <br/> <input type="checkbox">Видео в собраниях <br/> <input type="checkbox">Совместное использование в собраниях экрана <br/> <input type="checkbox">Аудиоконференции <br/><input type="checkbox">Приложения (приложения)<br> &nbsp;&nbsp; &nbsp; <input type="checkbox"> Вкладок<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Программы-роботы <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Соединители<br><input type="checkbox">Интеграция хранения настраиваемых облако <br>&nbsp;&nbsp; &nbsp; (Поле, общего банка данных, ShareFile, Google диск) <br/> <input type="checkbox">Интеграция электронной почты канала <br/> <input type="checkbox">Другое (укажите в столбце примечания). | |
> | Какие приложения вы развертывания для группы? | | |
> | Блокировали ли вы какие-то конкретные возможности Teams? <br/>Если Да, запишите подробные сведения в столбце примечания. | <input type="checkbox">Да <br/> <input type="checkbox">Нет ||
> | Какие используются клиенты Teams? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">операций ввода-вывода <br/> <input type="checkbox">Android (en) <br/> <input type="checkbox">Windows Mobile | |
> | Кому разрешено создавать команды? | <input type="checkbox">Всем пользователям в организации <br>&nbsp;&nbsp; &nbsp;(Значение по умолчанию) <br/> <input type="checkbox">Конкретные пользователи <br>&nbsp;&nbsp; &nbsp;(Укажите в столбце примечания). | |
> | Используете ли вы в Teams функции обеспечения безопасности и соответствия требованиям? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |

### <a name="skype-for-business-online-if-applicable"></a>Skype для бизнеса Online (при наличии)

Если это возможно, запись сведений о вашей Скайп для бизнеса в Интернет развертывания с помощью образца таблицы ниже. Если для бизнеса в Интернет развертывания еще не развернут Скайп, перейдите в этом разделе.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие типы пользователей, включены для Скайп <br>для бизнеса в Интернете? | <input type="checkbox">Все пользователи в организации <br/> <input type="checkbox">Конкретных пользователей/групп пользователей <br>&nbsp;&nbsp; &nbsp;(Укажите в столбце примечания) | |
> | Какие модальностей и функции в настоящий момент <br>используется сегодня? | <input type="checkbox">Обмен мгновенными сообщениями и присутствия (обмен мгновенными Сообщениями/P)<br/> <input type="checkbox">Собрания <br/> <input type="checkbox">Федерации <br/> <input type="checkbox">Запись собрания <br/> <input type="checkbox">Конференц-связи Microsoft звука <br/> <input type="checkbox">Аудиоконференции сторонних производителей <br>&nbsp;&nbsp; &nbsp;(Запишите подробные сведения в столбце примечания). <br/> <input type="checkbox">Тарифные планы (ранее — PSTN вызов) <br/> <input type="checkbox">Организационные автосекретари <br/> <input type="checkbox">Вызов очередей | |
> | Вы специально заблокирован для любого Скайп <br>Business возможностей в Интернете? <br>Если Да, запишите подробные сведения в столбце примечания. | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Какой метод — это с помощью или планируется использовать для <br>подключение к телефонной системой (ранее — облако УАТС) <br>ТСОП? <br/>Выберите все подходящие варианты. | <input type="checkbox">Тарифные планы (ранее — PSTN вызов) <br/> <input type="checkbox">Подключение к ТСОП в локальной (использование существующих <br>&nbsp;&nbsp; &nbsp;Скайп для бизнеса 2015 или Lync Server 2013 <br>&nbsp;&nbsp; &nbsp;развертывания) <br/> <input type="checkbox">Подключение к локальной ТСОП (с помощью соединителя облако) | |
> | Есть ли у вас телефонные номера, перенесенные в Майкрософт <br/>Это применимо для вызова планы и звука <br>Функции конференц-связи. | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Скайп для бизнеса в локальной (если применимо)

Если это возможно, запись сведений о вашей Скайп по развертыванию с помощью образца таблицы ниже. Если для бизнеса в локальной еще не развернут Скайп, перейдите в этом разделе.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие версии Lync или Скайп для бизнеса в настоящее время <br>Существуют развертываются локально? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Скайп для Business Server 2015 <br/> <input type="checkbox">Скайп для Business Server 2019 <br/> <input type="checkbox">Скайп облаке соединитель для выпуска для бизнеса | |
> | Настроено ли гибридное подключение со Skype для бизнеса Online? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Эта среда размещенных и управляется сторонних производителей? <br/>Если Да, запишите подробные сведения в столбце примечания. | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Функции и модальности Каковы в настоящее время используется <br>прямо сейчас? | <input type="checkbox">Обмен мгновенными сообщениями и присутствия (обмен мгновенными Сообщениями/P) <br/> <input type="checkbox">Собрания <br/> <input type="checkbox">Федерации <br/> <input type="checkbox">Запись собрания <br/> <input type="checkbox">Сохраняемый чат и групп чата <br/> <input type="checkbox">Конференц-связи Microsoft звука <br>&nbsp;&nbsp; &nbsp;(ранее — абонентской группы в конференц-связи) в вашей <br>&nbsp;&nbsp; &nbsp;локальной Lync Server или <br>&nbsp;&nbsp; &nbsp;Скайп по развертыванию <br/> <input type="checkbox">Аудиоконференции сторонних производителей <br>&nbsp;&nbsp; &nbsp;(Обратите внимание, Дополнительные сведения в столбце примечания) <br/> <input type="checkbox">Корпоративной голосовой связи используются локальные ТСОП <br>&nbsp;&nbsp; &nbsp;подключения <br/> <input type="checkbox">Тарифные планы (ранее — PSTN вызова) с помощью <br>&nbsp;&nbsp; &nbsp;Гибридное развертывание с Скайп для бизнеса в Интернете | |
> | Какие у вас развернуты версии пограничного сервера? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Скайп для Business Server 2015 <br/> <input type="checkbox">Скайп для Business Server 2019 | |
> | У вас Lync или Скайп для развертывания пограничного сервера Business <br>в нескольких центрах обработки данных? <br/>Если Да, запишите подробные сведения в столбце примечания. | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Выберите службы, которые сегодня предоставляет вашей роли пограничного сервера. | <input type="checkbox">Доступ внешних пользователей (корпоративные пользователи). <br/> <input type="checkbox">Доступ удаленных пользователей (анонимных внешний <br>&nbsp;&nbsp; &nbsp;участникам собрания) <br/> <input type="checkbox">Федерации <br/> <input type="checkbox">Ретрансляция мультимедиа | |
> | Какой из следующих голосовой связи, функции для звонков вы <br>в настоящее время имеют зависимости от? <br/>Обратите внимание, любые дополнительные зависимости в комментариях <br>столбец. | <input type="checkbox">Параметры «занят» <br/> <input type="checkbox">Парковка вызовов <br/> <input type="checkbox">Вызов раскладки или раскладки групповой звонок <br/> <input type="checkbox">Телефонов общего пользования или «горячего desking» <br/> <input type="checkbox">Сервисные группы или группы ответа <br/> <input type="checkbox">Внешний вид общей строки <br/> <input type="checkbox">Частная линия <br/> <input type="checkbox">Голосовая почта <br/> <input type="checkbox">Вызов с рабочего телефона <br/> <input type="checkbox">EMERGENCY или сведения о чисел <br>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox">Расширение набора номера <br/> <input type="checkbox">Автосекретарь <br/> <input type="checkbox">Абонентский доступ <br/> <input type="checkbox">Аналоговых устройств <br/> <input type="checkbox">Факс <br/> <input type="checkbox">Режим маски идентификатор звонящего или изменения <br/> <input type="checkbox">Маршрутизация на основе расположения <br/> <input type="checkbox">Маршрутизация по принципу наименьшей стоимости <br/> <input type="checkbox">Телефоны лифта | |

## <a name="networking-and-access-to-office-365-services"></a>Сети и доступ к службам Office 365

Используйте следующую таблицу для записи сведений о сети вашей организации и как они (или будет), подключенных к службам Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Как (или как будет) пользователи в области действия для миграции <br>доступ к группам, находясь в офисе? <br/>Выберите все подходящие варианты. | <input type="checkbox">Подключение с маршрутизацией преобразования сетевых адресов <br/> <input type="checkbox">Прокси-сервер <br/> <input type="checkbox">Общедоступный Wi-Fi <br/> <input type="checkbox">Управляемые (не для общих) Wi-Fi <br/> <input type="checkbox">ExpressRoute (Microsoft авторами) ||
> | Если доступ к Office 365 через прокси-сервер, существует ли <br>никаких уведомлений для обхода прокси-сервера? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Используется ли сейчас ExpressRoute? | <input type="checkbox">Да <br/> <input type="checkbox">Нет <br/> <input type="checkbox">Нет, но является планируемый | |
> | Была выполнена оценка готовности сети? <br/>Для получения дополнительных сведений см [Оценки готовности сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness). | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Пользователей, необходимо выполнить для использования виртуальной частной сети при подключении к <br>корпоративные ресурсы удаленно? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | При использовании VPN трафик команды исключаются из <br>VPN-Подключение прямой доступ к службам Office 365? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Поддерживает ли ваша сеть качество обслуживания (QoS)? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Можно приоритеты для трафика аудио- и видеоконференций групп <br>диск высокое качество взаимодействия? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Должны ли все расположения в области исходящего трафика Интернета <br>или для всей области централизовано исходящего трафика Интернета? | <input type="checkbox">Региональные доступ к Интернету <br/> <input type="checkbox">Централизованный доступ к Интернету | |

> [!TIP]
> Вычислите объем пропускной способности и другие требования к сети для голосовой почты облачных развертывания, в зависимости от сведений о вашей организации и Оценка использования посетите [Планировщик работы сети](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) в [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).

## <a name="endpoints"></a>Конечные точки

Используйте следующую таблицу для записи сведений о клиентами и конечными точками использования.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие операционные системы для настольных компьютеров вы сейчас используете? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (задать версию в столбце примечания). <br/> <input type="checkbox">Другие (запишите подробные сведения в столбце примечания). | |
> | Развертывание версии системы Microsoft Office <br>для этих устройств? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office для Mac 2011 г. <br/> <input type="checkbox">Office для Mac 2016 <br/> <input type="checkbox">Другие (запишите подробные сведения в столбце примечания). | |
> | Какие технологии развертывания Office уже используется <br>в вашей организации? | <input type="checkbox">MSI <br/> <input type="checkbox">Click-to-Run | |
> | Что такое разрешенных и поддерживаемых мобильных устройств <br>Платформа используется? <br/>Выберите все подходящие варианты. | <input type="checkbox">Windows <br/> <input type="checkbox">Mobile <br/> <input type="checkbox">операций ввода-вывода <br/> <input type="checkbox">Android (en) <br/> <input type="checkbox">Другие (запишите подробные сведения в столбце примечания). | |
> | В какой форме предоставляются мобильные устройства <br/>Выберите все подходящие варианты. | <input type="checkbox">Корпоративный устройств <br/> <input type="checkbox">Использование собственного устройства | |
> | Какие устройства ли пользователи в настоящее время используется для доступа к <br>службы голосовой связи и конференц-связи <br>(мобильные телефоны, гарнитуры, телефоны, видео)? | | |

## <a name="operations"></a>Операции

Используйте следующую таблицу для записи сведений о особенностей вашей среде.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Что такое для Lync Server, модель операции <br>Скайп для развертывания Office 365 или Business Server <br>прямо сейчас? | | |
> | Можно структурировать текущее расположение поддержки <br>Lync Server Скайп Business Server или Office 365? | | |
> | При развертывании в нескольких странах или регионах <br>каждой страны или региона имеет свой собственный ИТ и телефонной связи <br>персонала для работы с, или это управляемые централизованно? | <input type="checkbox">Региональные операции и поддержка <br/> <input type="checkbox">Централизованная операции и поддержка | |
> | Вы после [Вызова методика качества](quality-of-experience-review-guide.md)? | <input type="checkbox">Да <br/> <input type="checkbox">Нет | |
> | Назначен физическим или группы <br>Качество Champion роли для платформа для совместной работы <br>используется? | <input type="checkbox">Да <br/> <input type="checkbox">Нет ||
> | Как контролировать Lync Server, Скайп для <br>Business Server или Office 365 развертывания? | | |
> | Испытываете ли вы проблемы с качеством звонков? | <input type="checkbox">Да<br/> <input type="checkbox">Нет | |
> | Как и когда вы предоставляете учебного курса, чтобы вашей <br>Служба технической поддержки на новые службы и возможности? | | |

## <a name="adoption-and-readiness"></a>Подготовка и внедрения

Укажите в следующей таблице сведения о принятии системы персоналом и готовности вашей организации к ее использованию.

>
> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Что такое текущего активного использования <br>Скайп для бизнеса? | **__** % всего активных пользователей и пользователей с включенной поддержкой | |
> | Использовании вашей организации <br>Скайп для бизнеса? | Личные беседы <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Обмена мгновенными Сообщениями <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Вызова <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Общего доступа<br> Собрания <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Конференц-связи<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Общего доступа<br>&nbsp;&nbsp; &nbsp; <input type="checkbox"> Вызова | |
> | Есть ли у вашей организации внедрения пользователя <br>Управление изменениями рабочая группа и? | <input type="checkbox">Да<br/> <input type="checkbox">Нет | |
> | Как вы в настоящее время успеха меру для технологии <br>развертывания как Скайп для бизнеса? | | |
> | Какой процент базы пользователей вы сказали имеет <br>применяет Скайп для бизнеса? | | |
> | Каково мнение пользователей о Skype для бизнеса? | <input type="checkbox">Хороший <br/> <input type="checkbox">Neutral <br/> <input type="checkbox">Недопустимый | |
> | Следующие рекомендации, описывающего выгрузка данных <br>стратегия для вашей Скайп для бизнеса <br>развертывание? | <input type="checkbox">Широкой аудитории: электронной почты кампании с <br>&nbsp;&nbsp; &nbsp;ссылки на обучение <br/> <input type="checkbox">Расширенное: Широкой аудитории, а также различные <br>&nbsp;&nbsp; &nbsp;сведения о кампаний (плакаты, <br>&nbsp;&nbsp; &nbsp;событий, чемпионатов) и учебные курсы <br>&nbsp;&nbsp; &nbsp;(видеозаписи, руководства для пользователей, в лицо) <br/> <input type="checkbox">Настроенные: Развернут, а также нацелено <br>&nbsp;&nbsp; &nbsp;системы обмена сообщениями и обучающие материалы по пользователя <br/> <input type="checkbox">Другие <br>&nbsp;&nbsp; &nbsp;(Запишите подробные сведения в столбце примечания). | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Точка принятия решений</td><td><ul><li>Кто будет отвечать за выполнение оценки среды?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Следующий шаг</td><td><ul><li>Документирование результатов оценки производительности среды.</li></ul></td></tr>
</table>

После оценка среды, переходите к следующему шагу: [Подготовка к сети](upgrade-prepare-environment-prepare-network.md).
