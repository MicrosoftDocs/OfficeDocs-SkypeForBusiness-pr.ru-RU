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
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c537f37534c616965b74f5ea268f547cff28d41
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016143"
---
# <a name="cloud-voice-deployment"></a>Развертывание облачной системы голосовой связи

Microsoft Teams, центр для командной работы и взаимодействия в Office 365, теперь поддерживает аудиоконференции, а также телефонную систему с планами звонков и прямую маршрутизацию телефонной системы, удовлетворяя еще более широкий спектр потребностей бизнеса. Новые возможности звонков и собраний платформы Teams позволяют подключать сторонних участников по телефонной сети общего пользования (ТСОП).
 
Со временем мы будем обновлять эту страницу по мере выпуска в Teams новых функций облачной голосовой связи.



## <a name="audio-conferencing-in-microsoft-teams"></a>Аудиоконференции в Microsoft Teams


Аудиоконференции в Office 365 позволяют участникам присоединяться к вашим собраниям Teams с любого телефона.

Ниже указано, что именно вы получаете вместе с [аудиоконференциями](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) в Office 365.


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a>Телефонная система с Планами звонков в Microsoft Teams

Телефонная система — это компонент Office 365, позволяющий управлять маршрутизацией звонков, политиками и подготовкой пользователей. В него входит система управления телефонными звонками, маршрутизация звонков и настройка отдельных звонков.

Тарифные планы является дополнительной службы для функции телефонной системой, доставленных через рабочих групп и Скайп для бизнеса в Интернет. Тарифные планы требуется, что пользователь быть размещен в Скайп для бизнеса в Интернет для работы в группах Майкрософт. Тарифные планы обеспечивают для сотрудников в бизнесе с основной номер телефона, а также позволяет их выполнение и прием телефонных звонков за пределами вашей организации по ТСОП.

Дополнительные сведения см. в статьях [Возможности телефонной системы в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) и [Общие сведения о планах звонков в Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365).


## <a name="phone-system-direct-routing-direct-routing"></a>Прямая маршрутизация телефонной системы

Прямая маршрутизация работает с компонентом телефонной системы, позволяя пользователям вашей организации совершать и принимать звонки за пределами организации по телефонной сети общего пользования (ТСОП), при этом возможность подключения по ТСОП обеспечивается через сторонних поставщиков услуг.

Дополнительные сведения см. в статьях [Планирование прямой маршрутизации](direct-routing-plan.md) и [Настройка прямой маршрутизации](direct-routing-configure.md).

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a>Практическое руководство для аудиоконференций, планов звонков и прямой маршрутизации в Microsoft Teams

С помощью платформы реализация клиента Office 365 эту организован этого практического руководства и его три этапы&mdash;Предвидения, встроенный и значение диска. Он своей целью помогут спланировать, доставки и использовать успешной реализации звук, вызов планы и/или прямой маршрутизации.

> [!div class="mx-tableFixed"]
> |Выработка концепции  |Адаптация  |Извлечение выгоды  |
> |---------|---------|---------|
> |[Определение показателей успеха](1-envision-define-my-success-cloud-voice.md) <br> Принятие решений по службе для <br>&nbsp;&nbsp;[аудиоконференций](2-envision-make-my-service-decisions-audio-conferencing.md),<br>&nbsp;&nbsp;[планов звонков](2-envision-make-my-service-decisions-phone-system.md) или [прямой маршрутизации](2-envision-make-my-service-decisions-direct-routing.md) <br> [Оценка среды](3-envision-evaluate-my-environment.md) <br> [Планирование управления службами](4-envision-plan-my-service-management.md) <br> [Планирование взаимодействия с пользователями](5-envision-plan-my-users-experience.md) <br> [Документирование плана по достижению успеха](6-envision-document-my-success-plan.md)    | [Подготовка службы](1-onboard-prepare-my-service.md) <br> [Подготовка пользователей](2-onboard-prepare-my-users.md) <br> [Развертывание службы](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [Использование службы](1-drive-value-operate-my-service.md) <br> [Улучшение службы](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

Контент в упорядоченном виде и предназначен для ознакомления реализация-сквозного развертывания от начала до конца. Если вы уже активно выполняется развертывание, по-прежнему рекомендуется для ссылки применимых области контента.


> [!TIP]
> В этом практического руководства мы предоставляем выводится для каждого действия и ключевые обсуждений. Примеры в данном документе заключаются внутри выносок подсказки, и они могут использоваться в качестве шаблона, который можно повторно использовать. Вы увидите «TBA» (для добавления) сведения, которые необходимо выполнить как часть процесса планирования.
