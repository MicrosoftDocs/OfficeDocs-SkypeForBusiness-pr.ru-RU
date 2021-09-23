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
description: 'Узнайте, как настроить облачная голосовая почта для пользователей. '
ms.openlocfilehash: 37cf89d4c728cab491d0312762a2c845bb711dcd
ms.sourcegitcommit: 5f19df90443810e027085f8b38d22218e4123a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2021
ms.locfileid: "59482423"
---
# <a name="set-up-cloud-voicemail"></a>Настройка облачной голосовой почты

Эта статья адресовна администратору Microsoft 365 или Office 365, [](/microsoft-365/admin/add-users/about-admin-roles) как описано в статье Роли администраторов, которые хотят настроить облачная голосовая почта для всех в компании.

> [!NOTE]
> облачная голосовая почта поддерживает хранение сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние почтовые системы. 

> [!NOTE]
> Когда делегат отвечает на звонок от имени представителя, в облачная голосовая почта. Пользователи могут получать уведомления о пропущенных звонках.

## <a name="cloud-voicemail-for-teams-users"></a>облачная голосовая почта для Teams пользователей

Для Teams автоматически облачная голосовая почта и подготовка. Обратите внимание, телефонная система лицензия не требуется для облачная голосовая почта. 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Настройка облачная голосовая почта для Exchange Server почтовых ящиков

Ниже данная информация о настройке облачная голосовая почта для работы с пользователями, которые находятся в сети телефонная система но имеют свой почтовый ящик Exchange Server. 
  
1. Сообщения голосовой почты доставляются в почтовый Exchange пользователей через SMTP, маршрутный через Exchange Online Protection. Чтобы обеспечить успешную доставку этих сообщений, убедитесь, что соединители Exchange правильно настроены между серверами Exchange и Exchange Online Protection; [Настройте почтовые Flow с помощью соедините Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Чтобы включить функции голосовой почты, такие как настройка приветствий и визуальной голосовой почты в клиентах Skype для бизнеса, требуется подключение Microsoft 365 или Office 365 к почтовому ящику Exchange сервера через веб-службы Exchange. Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности Exchange Oauth, описанный в окне Настройка проверки подлинности [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)между организациями Exchange и Exchange Online, или запустить мастер гибридной конфигурации Exchange в Exchange 2013 CU5 или более новой. Кроме того, необходимо настроить интеграцию и Oauth между серверами Skype для бизнеса Online и Exchange, описанными в окне Настройка интеграции и [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)между Skype для бизнеса Online и Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Настройка облачная голосовая почта для Skype для бизнеса Server пользователей

Чтобы настроить Skype для бизнеса серверов для облачная голосовая почта, см. облачная голосовая почта планирования службы для пользователей [локальной сети.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Включение защищенной голосовой почты в организации

Когда кто-то покидает сообщение голосовой почты для пользователя в вашей организации, голосовая почта доставляется в почтовый ящик пользователя в виде вложения сообщения электронной почты. Используя правила потока почты для применения шифрования сообщений, вы можете запретить их пересылку другим получателям. Если включить защищенную голосовую почту, пользователи смогут прослушивать защищенные сообщения голосовой почты, позвонив в свой почтовый ящик голосовой почты или открыв их в Outlook, Outlook в Интернете или Outlook для Android или iOS. Защищенные сообщения голосовой почты нельзя открывать в Skype для бизнеса или Microsoft Teams.

Дополнительные сведения о шифровании сообщений см. в теме [Шифрование электронной почты.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)


Чтобы настроить защищенную голосовую почту, сделайте следующее:

1. Перейдите к учетной записи с разрешениями глобального администратора и войдите https://admin.microsoft.com в нее.
2. Выберите **Показать все,** а затем перейдите в центр **администрирования**  >  **Exchange**.
3. В Центре Exchange выберите правила **потока обработки**  >  **почты**.
4. Выберите Добавить , а затем выберите Шифрование сообщений Office 365 защиты прав и **+** прав **к сообщениям**.
5. Введите имя для нового правила потока почты, а затем в списке Применить это **правило,** если , выберите Свойства  >  **сообщенияВключите тип** сообщения  >  **Голосовая почта**. Выберите **ОК**.
6. В **области Сделать следующее** выберите Применить шифрование сообщений Office 365 и защиту **прав** к сообщению с помощью и выберите Выберите **один**. В **области Шаблон RMS** выберите Не **переадваровываться**. Выберите **ОК,** а затем **Сохранить**.
    > [!NOTE]
    > Если список **шаблонов RMS** пуст, необходимо настроить шифрование сообщений. Дополнительные сведения о настройке шифрования сообщений см. в следующих статьях:
    > - [Настройка новых возможностей шифрования сообщений](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Настройка шаблонов для Azure Information Protection и управление их использованием](/information-protection/deploy-use/configure-policy-templates)
    > - [Параметр "Не переадваровыть" для сообщений электронной почты](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

    > [!NOTE]
    > Чтобы форма голосовой почты была видна пользователям, организациям и организациям, необходимо настроить следующий реестр: [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Outlook\Addins] "AllowVoicemailForm"=dword:00000001                           

## <a name="help-your-users-learn-teams-voicemail-features"></a>Помощь пользователям в Teams голосовой почты

Пользователи могут управлять настройками голосовой почты, а также другими функциями звонков в Teams:

- [Управление настройками параметров звонка в Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). В этой статье объясняется, как управлять всеми функциями звонков Teams пользователями. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса

Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.

- [Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.

- [Обучение работе со Skype для бизнеса 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Возможности телефонной системы](here-s-what-you-get-with-phone-system.md)

[Планирование миграции Skype для бизнеса Server и Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)
