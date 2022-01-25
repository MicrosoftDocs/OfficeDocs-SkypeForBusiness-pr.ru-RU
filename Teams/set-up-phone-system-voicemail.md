---
title: Настройка облачной голосовой почты
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Узнайте, как настроить облачная голосовая почта для пользователей.
ms.openlocfilehash: cf4edb7043c3d9965f2f01710f1ed9e7fa7f96b8
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191080"
---
# <a name="set-up-cloud-voicemail"></a>Настройка облачной голосовой почты

Эта статья адресовна администратору Microsoft 365 или Office 365, как [](/microsoft-365/admin/add-users/about-admin-roles) описано в статье Роли администраторов, которые хотят настроить облачная голосовая почта для всех в компании. облачная голосовая почта требуется Exchange почтовых ящиков пользователей, в которые они вкладыют сообщения голосовой почты. Она не поддерживает сторонние почтовые системы. Описание Exchange Online лицензирования см. в Exchange Online [службы.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)

## <a name="cloud-voicemail-for-teams-users"></a>облачная голосовая почта для Teams пользователей

Для Teams пользователей облачная голосовая почта автоматически настроена и подготовка. Лицензия Microsoft Teams Телефон лицензия не требуется для облачная голосовая почта.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Помощь пользователям в Teams голосовой почты

Пользователи могут получить следующие сведения об использовании голосовой почты в Teams и управлении Teams.

- [Проверка голосовой почты в Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Управление настройками параметров звонка в Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>Настройка облачная голосовая почта для работы с пользователями локальной сети

С помощью облачная голосовая почта можно предоставлять функции голосовой почты пользователям, у которых есть почтовые ящики на серверах Exchange, или пользователям, которые используют Skype для бизнеса Server. В этом разделе приводится информация об этих сценариях. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Настройка облачная голосовая почта для Exchange Server почтовых ящиков

Ниже данная информация о настройке облачная голосовая почта для работы с Microsoft Teams Телефон пользователями, у которых есть почтовый ящик Exchange Server.

1. Сообщения голосовой почты доставляются в почтовый Exchange пользователей через SMTP, маршрутный через Exchange Online Protection. Чтобы обеспечить успешную доставку этих сообщений, убедитесь, что соединители Exchange правильно настроены между серверами Exchange и Exchange Online Protection; [Настройте почтовые Flow с помощью соедините Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. Чтобы включить функции голосовой почты, такие как настройка приветствий и визуальной голосовой почты в клиентах Skype для бизнеса, требуется подключение из Microsoft 365 или Office 365 к почтовому ящику Exchange сервера через веб-службы Exchange. Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности Exchange Oauth, описанный в окне Настройка проверки подлинности [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)между организациями Exchange и Exchange Online, или запустить мастер гибридной конфигурации Exchange в Exchange 2013 CU5 или более новой. Кроме того, необходимо настроить интеграцию и Oauth между серверами Skype для бизнеса Online и Exchange, описанными в окне Настройка интеграции и [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)между Skype для бизнеса Online и Exchange Server.

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Настройка облачная голосовая почта для Skype для бизнеса Server пользователей

Чтобы настроить Skype для бизнеса серверов для облачная голосовая почта, см. облачная голосовая почта планирования службы для пользователей [локальной сети.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Включение защищенной голосовой почты в организации

Когда кто-то покидает сообщение голосовой почты для пользователя в вашей организации, голосовая почта доставляется в почтовый ящик пользователя в виде вложения сообщения электронной почты. Используя правила потока почты для применения шифрования сообщений, вы можете запретить их пересылку другим получателям. Если включить защищенную голосовую почту, пользователи смогут прослушивать защищенные сообщения голосовой почты, позвонив в свой почтовый ящик голосовой почты или открыв их в Outlook, Outlook в Интернете или в Outlook для Android или iOS. Защищенные сообщения голосовой почты нельзя открывать в Skype для бизнеса или Microsoft Teams.

Дополнительные сведения о шифровании сообщений см. в теме Определение правил потока [почты для шифрования сообщений электронной почты.](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)
