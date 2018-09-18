---
title: Развертывание облачной системы голосовой связи
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: MyAdvisor
description: Практическое руководство по развертыванию функций облачной голосовой связи в Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9bf4d920ba8ce8e25d663a9bab1769f80d693a77
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892368"
---
# <a name="cloud-voice-deployment"></a>Развертывание облачной системы голосовой связи

Microsoft Teams, центр для командной работы и взаимодействия в Office 365, теперь поддерживает аудиоконференции, а также телефонную систему с планами звонков и прямую маршрутизацию телефонной системы, удовлетворяя еще более широкий спектр потребностей бизнеса. Новые возможности звонков и собраний платформы Teams позволяют подключать сторонних участников по телефонной сети общего пользования (ТСОП).
 
Со временем мы будем обновлять эту страницу по мере выпуска в Teams новых функций облачной голосовой связи.



## <a name="audio-conferencing-in-microsoft-teams"></a>Аудиоконференции в Microsoft Teams


Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.

Ниже указано, что именно вы получаете вместе с [аудиоконференциями](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) в Office 365.


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Телефонная система с Планами звонков в Microsoft Teams

Телефонная система — это компонент Office 365, позволяющий управлять маршрутизацией звонков, политиками и подготовкой пользователей. В него входит система управления телефонными звонками, маршрутизация звонков и настройка отдельных звонков.

Планы звонков представляют собой дополнительную службу для компонента телефонной системы, предоставляемую через Teams и Skype для бизнеса Online. Чтобы планы звонков работали в Microsoft Teams, соответствующий пользователь должен находиться в Skype для бизнеса Online. Планы звонков предоставляют пользователям в вашей организации основной телефонный номер и возможность совершать и принимать звонки за пределами организации по телефонной сети общего пользования (ТСОП).

Дополнительные сведения см. в статьях [Возможности телефонной системы в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) и [Общие сведения о планах звонков в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365).


## <a name="phone-system-direct-routing-direct-routing"></a>Прямая маршрутизация телефонной системы

Прямая маршрутизация работает с компонентом телефонной системы, позволяя пользователям вашей организации совершать и принимать звонки за пределами организации по телефонной сети общего пользования (ТСОП), при этом возможность подключения по ТСОП обеспечивается через сторонних поставщиков услуг.

Дополнительные сведения см. в статьях [Планирование прямой маршрутизации](direct-routing-plan.md) и [Настройка прямой маршрутизации](direct-routing-configure.md).

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Практическое руководство для аудиоконференций, планов звонков и прямой маршрутизации в Microsoft Teams

Это практическое руководство упорядочено по циклу взаимодействия с клиентом FastTrack Office 365 и трем его этапам &mdash; выработке концепции, адаптации и извлечении выгоды. Оно призвано помочь вам спланировать, осуществить и использовать успешную реализацию аудиоконференций, планов звонков или прямой маршрутизации.

> [!div class="mx-tableFixed"]
> |Выработка концепции  |Адаптация  |Извлечение выгоды  |
> |---------|---------|---------|
> |[Определение показателей успеха](1-envision-define-my-success-cloud-voice.md) <br> Принятие решений по службе для <br>&nbsp;&nbsp;[аудиоконференций](2-envision-make-my-service-decisions-audio-conferencing.md),<br>&nbsp;&nbsp;[планов звонков](2-envision-make-my-service-decisions-phone-system.md) или [прямой маршрутизации](2-envision-make-my-service-decisions-direct-routing.md) <br> [Оценка среды](3-envision-evaluate-my-environment.md) <br> [Планирование управления службами](4-envision-plan-my-service-management.md) <br> [Планирование взаимодействия с пользователями](5-envision-plan-my-users-experience.md) <br> [Документирование плана по достижению успеха](6-envision-document-my-success-plan.md)    | [Подготовка службы](1-onboard-prepare-my-service.md) <br> [Подготовка пользователей](2-onboard-prepare-my-users.md) <br> [Развертывание службы](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [Использование службы](1-drive-value-operate-my-service.md) <br> [Улучшение службы](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

Содержимое представлено в упорядоченном виде и призвано рассказать вам обо всем цикле развертывания от начала и до конца. Если вы уже активно проводите развертывание, мы все равно рекомендуем вам ознакомиться с соответствующими материалами.


> [!TIP]
> В этом практическом руководстве есть примеры результатов по каждому действию и обсуждаемому вопросу. В этом документе примеры находятся внутри выносных элементов «Совет», и вы можете использовать их как шаблоны в собственной работе. Вы увидите сообщение «Подлежит добавлению» на месте информации, которую вам нужно указать в рамках процесса планирования.
