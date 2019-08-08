---
title: Развертывание облачной системы голосовой связи
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: Rowille
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 476d65ee927fedf285cf66377c58c9f09698b046
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236768"
---
# <a name="cloud-voice-deployment"></a>Развертывание облачной системы голосовой связи

Microsoft Teams, центр для командной работы и взаимодействия в Office 365, теперь поддерживает аудиоконференции, а также телефонную систему с планами звонков и прямую маршрутизацию телефонной системы, удовлетворяя еще более широкий спектр потребностей бизнеса. Новые возможности звонков и собраний платформы Teams позволяют подключать сторонних участников по телефонной сети общего пользования (ТСОП).


> [!Tip] 
> Для ознакомления с телефонными системами ознакомьтесь со следующими семинарами: [Введение в телефонную систему в Microsoft Teams](https://aka.ms/teams-phone-system)
 
Мы будем обновлять эту страницу как дополнительные функции голосовой связи по облаку для Teams с течением времени.



## <a name="audio-conferencing-in-microsoft-teams"></a>Аудиоконференции в Microsoft Teams


Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.

Вот что можно сделать с помощью [голосовой конференции](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) в Office 365.


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Телефонная система с планами звонков (планы звонков) в Microsoft Teams

Телефонная система — это функция Office 365, обеспечивающая возможность управления маршрутизацией звонков, политиками и пользователями. Сюда входит система управления телефонным подключением, маршрутизация звонков и управление звонками.

Планы звонков — это надстройка для функции телефонной системы, предоставляемая в Teams и Skype для бизнеса Online. Для работы планов звонков в Skype для бизнеса Online требуется, чтобы пользователь был размещен в Microsoft Teams. Планы звонков предоставляют сотрудникам компании номер основного номера и могут совершать и принимать телефонные звонки за пределами вашей организации по протоколу PSTN.

Чтобы узнать больше, ознакомьтесь [с возможностями, которые вы получаете в телефонной системе Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) и [телефонной системы и планов звонков](calling-plan-landing-page.md)


## <a name="phone-system-direct-routing-direct-routing"></a>Прямая маршрутизация на телефонную систему (прямая маршрутизация)

Прямая маршрутизация работает с функцией телефонной системы, чтобы дать сотрудникам вашей организации возможность совершать и принимать телефонные звонки за пределами Организации через сеть PSTN, в которой связь по протоколу PSTN обеспечивается с помощью сторонних поставщиков услуг.

Чтобы узнать больше, прочтите [маршрут на прямую маршрутизацию](direct-routing-plan.md) и [Настройте прямую маршрутизацию](direct-routing-configure.md).

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Практические рекомендации по голосовой конференции, тарифные планы и прямую маршрутизацию в Microsoft Teams

Это практическое руководство организовано с помощью инфраструктуры Office 365 FastTrack и ее трех фаз&mdash;, а также их значения. Она предназначена для того, чтобы помочь вам планировать, добиваться и выполнять успешные видеоконференции, планы звонков или прямую маршрутизацию.

> [!div class="mx-tableFixed"]
> |Выработка концепции  |Адаптация  |Извлечение выгоды  |
> |---------|---------|---------|
> |[Определение показателей успеха](1-envision-define-my-success-cloud-voice.md) <br> Принятие моих решений в службе <br>&nbsp;&nbsp;[Голосовые конференции](2-envision-make-my-service-decisions-audio-conferencing.md),<br>&nbsp;&nbsp;[Планы звонков](2-envision-make-my-service-decisions-phone-system.md)или [Прямая маршрутизация](2-envision-make-my-service-decisions-direct-routing.md) <br> [Оценка среды](3-envision-evaluate-my-environment.md) <br> [Планирование управления службами](4-envision-plan-my-service-management.md) <br> [Планирование работы пользователей](5-envision-plan-my-users-experience.md) <br> [Документирование плана по достижению успеха](6-envision-document-my-success-plan.md)    | [Подготовка службы](1-onboard-prepare-my-service.md) <br> [Подготовка пользователей](2-onboard-prepare-my-users.md) <br> [Развертывание службы](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [Использование службы](1-drive-value-operate-my-service.md) <br> [Улучшение службы](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

Содержимое представлено в упорядоченном виде, и оно предназначено для создания сквозного развертывания с начала до конца. Если вы уже активно развернут, мы по-прежнему рекомендуем вам ссылаться на нужные области контента.


> [!TIP]
> В этом практическом руководстве мы предоставляем примеры выходных данных для каждого действия и ключевой дискуссии. Примеры в этом документе заключены между выносками TIP и служат шаблоном, который можно использовать повторно. Вы увидите "Тба" (Добавить) для получения информации, которая должна быть выполнена в рамках процесса планирования.
