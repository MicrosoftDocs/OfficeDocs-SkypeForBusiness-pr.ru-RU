---
title: Обновление Microsoft Teams | Оценка среды, вопросы обнаружения
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Воспользуйтесь этим руководством, чтобы узнать о требованиях для правильной оценки текущей среды для перехода на Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49f69d679f22def35bd31efaef8b3046ddf9fdd0
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666081"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>Оценка среды перед обновлением в Teams

![Обновление схемы поездки с акцентом на этапе технической подготовки](media/upgrade-banner-tech-readiness.png "Этапы путешествия по обновлению с акцентом на этапе технической подготовки")

Эта статья относится к техническому этапу подготовки к обновлению, действиям, завершенным параллельно с этапом готовности пользователей. Прежде чем продолжить, подтвердите, что вы выполнили следующие действия из предыдущих стадий.

- [Вовлеченные заинтересованные лица в проект](upgrade-enlist-stakeholders.md)
- [Определение области охвата проекта](https://aka.ms/SkypetoTeams-Scope)
- [Сосуществование и взаимодействие Skype для бизнеса и рабочих групп](https://aka.ms/SkypeToTeams-Coexist)
- [Выбрано путешествие с обновлением](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

В этой статье приводятся общие сведения о требованиях для правильной оценки текущей среды для операционных групп. Оценивая вашу среду, вы определяете риски и требования, которые повлияют на общее развертывание. Определив эти элементы заранее, вы можете настроить планирование на успех.

## <a name="introduction-to-the-discovery-questionnaire"></a>Общие сведения о анкете обнаружения

Для получения ключевых результатов (OKRs) вы раньше внесли ключевые решения для обслуживания. Следующий этап — это возможность оценить все аспекты, связанные с инфраструктурой ИТ, сетью и операциями, чтобы убедиться в том, что ваша организация готова к реализации решения. Обнаружение — это один из самых первых, ключевых шагов, которые вы собираетесь планировать в Teams. Обнаружение среды должно включать оценку готовности к использованию сети, чтобы убедиться в том, что сеть сможет поддерживать обновление до Teams. Вы выполняете подробное обнаружение среды, чтобы лучше понять ее текущее состояние и выявить все проблемы или (еще более важные), которые могут быть заблокированы для выполнения выпуска команды.

Вы определяете технические риски в рамках оценки среды и оценки готовности к внедрению, а также Разработайте план снижения риска для каждого определенного риска. Эти сведения следует включить в реестр рисков.

Все, что связано с существующей инфраструктурой совместной работы и Microsoft 365 или Office 365 (организация, сеть, конечные точки, операции и внедрение и готовность), входят в состав анкеты по обнаружению окружающей среды. Анкета делится на несколько разделов, чтобы подтвердить готовность Организации к развертыванию Teams в нескольких основных областях. Вы можете работать с вашей командой проекта, чтобы предоставить запрашиваемые сведения как можно более детально, чтобы упростить планирование.

> [!TIP]
> Вы можете начать с копирования анкеты в документ Microsoft Word. Попробуйте ответить на все вопросы и захватить все детали по мере их перемещения.

## <a name="project-team"></a>Группа проекта

Убедитесь, что вы активировали нужных пользователей для своей группы проекта. Проверьте, какие действия были выполнены в разделе [Прикрепление заинтересованных лиц проекта](upgrade-enlist-stakeholders.md).

## <a name="microsoft-365-or-office-365-organization-details"></a>Сведения об организации Microsoft 365 или Office 365

При работе с этой анкетой мы настоятельно рекомендуем использовать активную организацию Microsoft 365 или Office 365. Если вы еще не активировали или не настроили организацию Microsoft 365 или Office 365, ознакомьтесь [с Разпланированием настройки microsoft 365 для бизнеса](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

В следующей таблице собраны сведения о Microsoft 365 или Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Обратите внимание на производственную организацию Microsoft 365 или Office 365 <br>имя и идентификатор в столбце Answer (ответ) <br/>Если у вас больше одного клиента <br>связанных с вашей организацией, <br>Запишите все идентификаторы. | Имя клиента: <br/>Идентификатор клиента:| |
> | В каких регионах развернутые клиенты?| | |
> | Являются клиентами Microsoft 365 или Office 365 с многоклиентским или <br>Балансировщика? | <input type="checkbox">Многоклиентский<br/> <input type="checkbox">Балансировщика | |
> | Какие продукты Microsoft Online вы используете сейчас? <br/>Обратите внимание на количество пользователей, включенных для каждого из них. <br>"служба" в столбце "Примечания". | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype для бизнеса <br>&nbsp; &nbsp; &nbsp;В Интернете <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive для бизнеса <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Другие| |
> | Какой уровень лицензирования включен для Skype для <br>Пользователи из сферы бизнеса Online? | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 <br/> <input type="checkbox">Отдельно | Количество пользователей <br>для каждого SKU выполните указанные ниже действия. |
> | Что такое текущий лес Active Directory <br>функциональный уровень в среде? <br/>Если у вас несколько лесов, обратите внимание на эти сведения <br>в столбце Примечания. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Что вы используете для работы с каталогом <br>Синхронизация сегодня |<input type="checkbox">Нет синхронизации (только в облаке) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp; Подключен <br/> <input type="checkbox">Другое (укажите в поле <br>&nbsp;&nbsp; &nbsp; Столбец примечаний.)| |
> | Развернуто ли сейчас федеративное удостоверение <br/>(Службы федерации Active Directory или <br>третьих сторон) | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Если вы используете федеративное удостоверение, что такое <br>инфраструктура Федерации? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Сторонняя Федерация <br>&nbsp;&nbsp; &nbsp; Gateway (шлюз) <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в <br>&nbsp;&nbsp; &nbsp; Столбец примечаний.) | |
> | Если в настоящее время поддерживается активный Microsoft 365 или Office 365 <br>Клиент — домен SMTP/SIP для вашего <br>Целевые пользователи, связанные с клиентом? | <input type="checkbox">Н/д – нет Microsoft 365 или Office 365 <br>&nbsp;&nbsp; &nbsp; клиент на своем расположении <br/> <input type="checkbox">Нет, SMTP и SIP пользователя <br>&nbsp;&nbsp; &nbsp; домен не связан <br>&nbsp;&nbsp; &nbsp; с клиентами в <br>&nbsp;&nbsp; &nbsp; Microsoft 365 или Office 365 <br/> <input type="checkbox">Да, SMTP и SIP пользователя <br>&nbsp;&nbsp; &nbsp; домен сопоставлен <br>&nbsp;&nbsp; &nbsp; с существующим клиентом <br>&nbsp;&nbsp; &nbsp; в Microsoft 365 или Office 365 | |
> | Совпадают ли UPN пользователей с основным SMTP-адресом? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет <br/> <input type="checkbox">Нестабильно | |

## <a name="existing-collaboration-platform-summary"></a>Существующая общая платформа для совместной работы

В следующей таблице собраны сведения о существующем развертывании платформы совместной работы.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Развернута ли система Microsoft Teams? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Развернута ли система Skype для бизнеса? <br/>Для локальных и гибридных развертываний убедитесь, что <br>Обратите внимание на версию и накопительное обновление (SP1). <br>сведения в столбце "Примечания". | <input type="checkbox">Да, Microsoft 365 или Office 365 <br/> <input type="checkbox">Да, гибридная (с Microsoft 365 или Office 365) <br/> <input type="checkbox">Да, в локальной среде <br/> <input type="checkbox">Да, в сети, выделено <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Да, размещено, выделено <br>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox">"Да", "размещено", "общий" (третью сторона) <br/> <input type="checkbox">Нет, другие | |
> | Развернута ли система Microsoft Exchange? <br/>Для локальных и гибридных развертываний убедитесь, что <br>Вы запомните сведения о версии и SP1 в примечаниях. <br>столбца. | <input type="checkbox">Да, Microsoft 365 или Office 365 <br/> <input type="checkbox">Да, гибридная (с Microsoft 365 или Office 365) <br/> <input type="checkbox">Да, в локальной среде <br/> <input type="checkbox">Да, в сети, выделено <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Да, размещено, выделено <br>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox">"Да", "размещено", "Общие" <br>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox">Нет, другие | |
> | Развернута ли система SharePoint? <br/>Для локальных и гибридных развертываний убедитесь, что <br>Вы запомните сведения о версии и SP1 в примечаниях. <br>столбца. | <input type="checkbox">Да, Microsoft 365 или Office 365 <br/> <input type="checkbox">Да, гибридная (с Microsoft 365 или Office 365) <br/> <input type="checkbox">Да, в локальной среде <br/> <input type="checkbox">Да, в сети, выделено <br>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox">Да, размещено, выделено <br>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox">"Да", "размещено", "Общие" <br>&nbsp;&nbsp; &nbsp; (третья сторона) <br/> <input type="checkbox">Нет, другие | |
> | Развернут ли Microsoft 365 или Office 365 OneDrive для бизнеса? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Развернуты ли другие платформы сторонних разработчиков <br>и используете сегодня? Если да, обратите внимание на количество пользователей <br>Эти платформы и сведения об использовании в примечаниях <br>столбца. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Имеющие <br/> <input type="checkbox">Другие (укажите в комментариях <br>&nbsp;&nbsp; &nbsp; столбец.) | Количество пользователей: <br/>Сведения|
> | Вы планируете переместить пользователей из этих сторонних <br>платформах для Teams? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Что такое текущее решение для телефонной связи и конференций <br>пользователей, которые находятся в области действия данной инициативы? | | |
> | У вас есть [SBCs, которые поддерживают прямую](direct-routing-plan.md#supported-session-border-controllers-sbcs) переадресацию, развернутую для Ваших офисов, которые находятся в области действия для этой инициативы? <br>Если да, обратите внимание на сведения в столбце Примечания.| <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет ||

## <a name="collaboration-platform-deployment-details"></a>Сведения о развертывании платформы совместной работы

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (при наличии)

Если применимо, запишите сведения о развертывании Teams с помощью примера в приведенной ниже таблице. Если вы еще не развернули команды, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каким группам пользователей доступна система Teams? | <input type="checkbox">Все пользователи в Организации <br/> <input type="checkbox">Конкретные пользователи и группы пользователей <br>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Примечания") ||
> | Какие функции Teams и модальностей используются? | <input type="checkbox">Беседы на основе канала <br/> <input type="checkbox">Закрытый чат <br/> <input type="checkbox">Гостевой доступ <br/> <input type="checkbox">Собрания канала <br/> <input type="checkbox">Личные собрания <br/> <input type="checkbox">Частный Звонок <br/> <input type="checkbox">Рекламный канал обсудим <br/> <input type="checkbox">Видео о собраниях <br/> <input type="checkbox">Демонстрация экрана в собраниях <br/> <input type="checkbox">Голосовые конференции <br/><input type="checkbox">Приложения (приложения)<br> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Закладок<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Ботов <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Плат<br><input type="checkbox">Интеграция настраиваемого облачного хранилища <br>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google диск, Egnyte (скоро) <br/> <input type="checkbox">Интеграция с электронной почтой канала <br/> <input type="checkbox">Другие (укажите в столбце Примечания). | |
> | Какие приложения вы развернули в Teams? | | |
> | Блокировали ли вы какие-то конкретные возможности Teams? <br/>Если да, обратите внимание на сведения в столбце Примечания. | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет ||
> | Какие используются клиенты Teams? | <input type="checkbox">Сайта <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Макинтоша <br/> <input type="checkbox">Ввода <br/> <input type="checkbox">ОС <br/> <input type="checkbox">Windows Mobile | |
> | Кому разрешено создавать команды? | <input type="checkbox">Все пользователи в Организации <br>&nbsp;&nbsp; &nbsp; (Это значение по умолчанию) <br/> <input type="checkbox">Определенные пользователи <br>&nbsp;&nbsp; &nbsp; (Укажите в столбце Примечания.) | |
> | Используете ли вы в Teams функции обеспечения безопасности и соответствия требованиям? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |

### <a name="skype-for-business-online-if-applicable"></a>Skype для бизнеса Online (при наличии)

Если применимо, запишите сведения о развертывании Skype для бизнеса Online с помощью примера в таблице ниже. Если вы еще не развернули развертывание Skype для бизнеса Online, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие типы пользователей разрешены для Skype <br>для бизнеса Online? | <input type="checkbox">Все пользователи в Организации <br/> <input type="checkbox">Конкретные пользователи и группы пользователей <br>&nbsp;&nbsp; &nbsp; (Укажите в столбце "Примечания") | |
> | Что в настоящее время модальностей и компоненты <br>используете сегодня? | <input type="checkbox">Обмен мгновенными сообщениями и присутствие (IM/P)<br/> <input type="checkbox">Встреч <br/> <input type="checkbox">Федеративные <br/> <input type="checkbox">Запись собрания <br/> <input type="checkbox">Голосовая конференция Майкрософт <br/> <input type="checkbox">Голосовой Конференц-связь третьих лиц <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце Примечания.) <br/> <input type="checkbox">Планы звонков (ранее КОММУТИРУЕМых звонков) <br/> <input type="checkbox">Автоматические ассистенты Организации <br/> <input type="checkbox">Очереди звонков | |
> | Вы специально заблокировали любые Skype для <br>Возможности для бизнеса Online <br>Если да, обратите внимание на сведения в столбце Примечания. | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Какой метод вы используете или планируете использовать для <br>Подключите телефонную систему (прежнее название — облачная УАТС) <br>сеть PSTN? <br/>Выберите все подходящую силу. | <input type="checkbox">Планы звонков (ранее КОММУТИРУЕМых звонков) <br/> <input type="checkbox">Локальная сеть PSTN (использование существующих <br>&nbsp;&nbsp; &nbsp; Skype для бизнеса 2015 или Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; развертывание) <br/> <input type="checkbox">Локальная сеть PSTN (использование облачного соединителя) | |
> | Есть ли у вас телефонные номера, перенесенные в Майкрософт <br/>Это применимо к тарифным планам и звуку <br>Функции Конференции. | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Локальная среда Skype для бизнеса (если применимо)

Если применимо, запишите сведения о развертывании Skype для бизнеса с помощью примера в приведенной ниже таблице. Если вы еще не развернули локальную версию Skype для бизнеса, пропустите этот раздел.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие версии Lync и Skype для бизнеса в настоящее время <br>развернуты в локальной среде? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype для бизнеса Server 2015 <br/> <input type="checkbox">Skype для бизнеса Server 2019 <br/> <input type="checkbox">Skype для бизнеса Cloud Connector Edition | |
> | Настроено ли гибридное подключение со Skype для бизнеса Online? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Размещается ли эта среда и управляется третьими лицами? <br/>Если да, обратите внимание на сведения в столбце Примечания. | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Какие модальностей и функции в настоящее время используются <br>современного? | <input type="checkbox">Обмен мгновенными сообщениями и присутствие (IM/P) <br/> <input type="checkbox">Встреч <br/> <input type="checkbox">Федеративные <br/> <input type="checkbox">Запись собрания <br/> <input type="checkbox">Сохраняемый чат или групповой чат <br/> <input type="checkbox">Голосовая конференция Майкрософт <br>&nbsp;&nbsp; &nbsp; (ранее в конференц-связи) на вашем <br>&nbsp;&nbsp; &nbsp; локальный сервер Lync Server или <br>&nbsp;&nbsp; &nbsp; Развертывание Skype для бизнеса <br/> <input type="checkbox">Голосовой Конференц-связь третьих лиц <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце Примечания). <br/> <input type="checkbox">Корпоративная голосовая связь с использованием локальной сети PSTN <br>&nbsp;&nbsp; &nbsp; подключение <br/> <input type="checkbox">Планы звонков (ранее КОММУТИРУЕМых звонков) через <br>&nbsp;&nbsp; &nbsp; Гибридная работа в Skype для бизнеса Online | |
> | Какие у вас развернуты версии пограничного сервера? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype для бизнеса Server 2015 <br/> <input type="checkbox">Skype для бизнеса Server 2019 | |
> | Развертывание Lync или Skype для бизнеса Edge <br>в более чем один центр обработки данных? <br/>Если да, обратите внимание на сведения в столбце Примечания. | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Выберите службы, которые ваша роль пограничного пользователя предоставляет сегодня. | <input type="checkbox">Внешний доступ для пользователей (корпоративные пользователи) <br/> <input type="checkbox">Удаленный доступ пользователя (анонимный внешний <br>&nbsp;&nbsp; &nbsp; Участники собрания) <br/> <input type="checkbox">Федеративные <br/> <input type="checkbox">Ретрансляция мультимедиа | |
> | Какие из приведенных ниже функций голосовой связи можно использовать для звонков <br>Сейчас есть зависимости? <br/>Запишите все дополнительные зависимости в примечаниях. <br>столбца. | <input type="checkbox">Параметры занятости <br/> <input type="checkbox">Метод парковки <br/> <input type="checkbox">Отправка звонка или группового звонка <br/> <input type="checkbox">Обычные телефоны или "горячий стационарный" <br/> <input type="checkbox">Группы ответа или группы слежения <br/> <input type="checkbox">Вид общей линии <br/> <input type="checkbox">Частная линия <br/> <input type="checkbox">Голосовую почту <br/> <input type="checkbox">Звонок с помощью рабочих <br/> <input type="checkbox">Экстренные и информационные номера <br>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox">Добавочный набор номера <br/> <input type="checkbox">Автоматический секретарь <br/> <input type="checkbox">Абонентский доступ <br/> <input type="checkbox">Аналоговые устройства <br/> <input type="checkbox">Сообщений <br/> <input type="checkbox">Маскирование и изменение идентификатора вызывающего абонента <br/> <input type="checkbox">Маршрутизация на основе местоположения <br/> <input type="checkbox">Маршрутизация наименее затрат <br/> <input type="checkbox">Подъемные телефоны | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Работа в сети и доступ к службам Microsoft 365 и Office 365

В таблице ниже приведены сведения о том, как получить доступ к данным о сети организации, а также о том, как ваши пользователи будут подключены к Microsoft 365 или службам Office 365.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Как будут (или как это сделать) пользователи в области для миграции <br>доступ к Teams, когда они находятся в Office? <br/>Выберите все подходящую силу. | <input type="checkbox">Маршрутизируемое подключение NAT <br/> <input type="checkbox">Прокси-сервер <br/> <input type="checkbox">Общедоступный Wi-Fi <br/> <input type="checkbox">Управляемый (не общедоступный) Wi-Fi <br/> <input type="checkbox">ExpressRoute (пиринг Майкрософт) ||
> | Если доступ к Microsoft 365 или Office 365 осуществляется через прокси-сервер, есть ли у вас <br>как обойти прокси-сервер? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Используется ли сейчас ExpressRoute? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет <br/> <input type="checkbox">Нет, но запланировано | |
> | Выполнили ли вы оценку готовности к сети? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Пользователи должны использовать VPN при подключении к <br>корпоративные ресурсы удаленно? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | При использовании VPN можно исключить трафик группы из <br>VPN для доступа к службам Microsoft 365 и Office 365 напрямую? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Поддерживает ли ваша сеть качество обслуживания (QoS)? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Можно назначать приоритеты для звуковых и видеофайлов в Teams <br>для обеспечения высокого качества работы? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Все расположения в регионе имеют интернет-выхода, <br>или это Интернет-выхода, централизованно для всего региона? | <input type="checkbox">Региональный доступ к Интернету <br/> <input type="checkbox">Централизованный доступ к Интернету | |

## <a name="endpoints"></a>Конечные точки

Чтобы получить сведения о клиентах и конечных точках, используйте следующую таблицу.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какие операционные системы для настольных компьютеров вы сейчас используете? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (укажите версию в столбце "Примечания"). <br/> <input type="checkbox">Linux (укажите распределение в столбце Примечания). <br/> <input type="checkbox">Другие (Обратите внимание на сведения в столбце Примечания). | |
> | Какая версия Microsoft Office развернута <br>на эти устройства? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office для Mac 2011 <br/> <input type="checkbox">Office для Mac 2016 <br/> <input type="checkbox">Другие (Обратите внимание на сведения в столбце Примечания). | |
> | Какая технология развертывания Office используется <br>в вашей организации? | <input type="checkbox">УСТАНОВЩИКА <br/> <input type="checkbox">"Нажми и работай" | |
> | Каковы разрешенные и поддерживаемые мобильные устройства <br>используются платформы? <br/>Выберите все подходящую силу. | <input type="checkbox">Windows <br/> <input type="checkbox">Mobile <br/> <input type="checkbox">Ввода <br/> <input type="checkbox">ОС <br/> <input type="checkbox">Другие (Обратите внимание на сведения в столбце Примечания). | |
> | В какой форме предоставляются мобильные устройства <br/>Выберите все подходящую силу. | <input type="checkbox">Корпоративные устройства <br/> <input type="checkbox">Перевод собственного устройства | |
> | Устройства, используемые в настоящее время для доступа пользователей <br>Услуги голосовой связи и конференций <br>(трубки, гарнитуры, телефоны, видео) | | |

## <a name="operations"></a>Операции

Ниже приведена таблица, в которой собраны сведения о рабочих аспектах среды.

> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Какова модель операций для вашего сервера Lync, <br>Развертывание Skype для бизнеса Server, Microsoft 365 или Office 365 <br>современного? | | |
> | Вы можете структурировать текущее расположение для поддержки <br>Lync Server, Skype для бизнеса Server, Microsoft 365 или Office 365? | | |
> | Если вы развертываете в нескольких странах или регионах, <br>у каждой страны или региона есть своя собственная и телефонная связь <br>персонал для работы или будет централизованно управлять? | <input type="checkbox">Региональные операции и поддержка <br/> <input type="checkbox">Централизованные операции и поддержка | |
> | Вы подписаны на [методологию качества связи](quality-of-experience-review-guide.md)? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет | |
> | Вы назначили отдельного пользователя или группу <br>Роль лидера качества для платформы совместной работы <br>используется? | <input type="checkbox">Кнопки <br/> <input type="checkbox">Нет ||
> | Как отслеживать сервер Lync, Skype для <br>Бизнес-сервер, Microsoft 365 или развертывание Office 365? | | |
> | Испытываете ли вы проблемы с качеством звонков? | <input type="checkbox">Кнопки<br/> <input type="checkbox">Нет | |
> | Как и когда вы предоставляете обучение <br>Служба поддержки по новым услугам и возможностям? | | |

## <a name="adoption-and-readiness"></a>Внедрение и готовность

Укажите в следующей таблице сведения о принятии системы персоналом и готовности вашей организации к ее использованию.

>
> | Вопрос | Ответ | Комментарии |
> |---|---|---|
> | Каково текущее активное использование <br>Skype для бизнеса? | Общее количество активных пользователей **__** % и включенных пользователей | |
> | Как ваша организация использует <br>Skype для бизнеса? | Личные беседы <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> БЕСЕД <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Связь <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Общего доступа<br> Собрания <br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Невероятно<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Общего доступа<br>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Связь | |
> | В вашей организации есть внедрение пользователей <br>и изменить группу управления? | <input type="checkbox">Кнопки<br/> <input type="checkbox">Нет | |
> | Как в настоящее время вы измеряете успешность технологии <br>разработано как Skype для бизнеса? | | |
> | Какой процент от вашей пользовательской базы <br>принял (-а) Skype для бизнеса? | | |
> | Каково мнение пользователей о Skype для бизнеса? | <input type="checkbox">Правильного <br/> <input type="checkbox">Нейтрал <br/> <input type="checkbox">Сбой | |
> | Какое из приведенных ниже значений лучше описывает выпуск <br>стратегия, используемая в Skype для бизнеса <br>среде? | <input type="checkbox">Широкий доступ: кампания по электронной почте с <br>&nbsp;&nbsp; &nbsp; ссылки на учебные материалы <br/> <input type="checkbox">Развернуто: широкий доступ плюс широкий спектр <br>&nbsp;&nbsp; &nbsp; число кампаний о осведомленности (плакатов, <br>&nbsp;&nbsp; &nbsp; события, лидерамиы) и обучение <br>&nbsp;&nbsp; &nbsp; (видео, руководства пользователя, в личном) <br/> <input type="checkbox">Адаптированные: развернутые, и целевые <br>&nbsp;&nbsp; &nbsp; Обмен сообщениями и обучение по персонажам <br/> <input type="checkbox">Другие <br>&nbsp;&nbsp; &nbsp; (Обратите внимание на сведения в столбце Примечания.) | |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Точка принятия решений</td><td><ul><li>Кто будет отвечать за выполнение оценки среды?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Следующее действие</td><td><ul><li>Задокументируйте результаты оценки среды.</li></ul></td></tr>
</table>

После оценки среды переходите к следующему шагу: [Подготовка сети](prepare-network.md).
