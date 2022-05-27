---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Доверенное приложение — это приложение, основанное на пакете SDK 3.0 Core API Microsoft Unified Communications Managed API (UCMA), которому доверяет Skype для бизнеса Server.
ms.openlocfilehash: 909ade1fbb44410d6b2acb695b8111e43d766e50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674541"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Управление доверенными приложениями в Skype для бизнеса Server

*Доверенное приложение* — это приложение на основе пакета SDK UCMA 3.0 Core, которое является доверенным для Skype для бизнеса Server. Дополнительные сведения о приложениях UCMA см. в разделе "Документация по пакету SDK для 3.0 Core API Unified Communications Managed API 3.0 Core" https://go.microsoft.com/fwlink/p/?linkId=210320.

Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена". 

Из этой статьи вы узнаете, как настроить новый доверенный сервер приложений, просмотреть список доверенных приложений и просмотреть сведения о доверенных приложениях. 

## <a name="configure-a-new-trusted-application-server"></a>Настройка нового доверенного сервера приложений

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Начните построитель топологий **: нажмите** кнопку "Пуск", выберите пункт "Все программы **", Skype для бизнеса Server** **и нажмите** кнопку **Skype для бизнеса Server построитель топологий**.

3.  Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.

4.  В **диалоговом** окне "Сохранить топологию как" выберите нужный построитель топологий и нажмите кнопку **"Сохранить"**.

5.  В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.

6.  В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).

7.  На странице **"Выбор следующего прыжка**" в списке выберите Skype для бизнеса Server интерфейсного пула.

8.  Нажмите кнопку **Готово**.

9.  Выберите верхний узел **Skype для бизнеса Server**, а затем в меню "Действия" щелкните "**Опубликовать топологию"**.
    
    Пул **доверенных приложений должен** быть успешно создан и связан с правильным пулом переднего плана.


## <a name="view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

С помощью Skype для бизнеса Server панель управления просмотреть список доверенных приложений, развернутых в среде Skype для бизнеса Server. Доверенное приложение — это приложение, основанное на пакете SDK 3.0 Core API Microsoft Unified Communications Managed API (UCMA), которому доверяет Skype для бизнеса Server. В списке ниже приведены сведения об этом отношении доверия.

  - Доверенные приложения не будут подавляции для проверки подлинности Skype для бизнеса Server.

  - Доверенные приложения не регулируются Skype для бизнеса Server для транзакций SIP, подключений или исходящих вызовов голосовой связи по протоколу VoIP.

  - Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.

  - Доверенные приложения устойчивы и надежны.

В Skype для бизнеса Server панель управления вы увидите имя приложений, пул, в котором они выполняются, и используемый порт.


### <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

1.  Из учетной записи пользователя, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании. Дополнительные сведения о предопределенных административных ролях, доступных в Skype для бизнеса Server, см. в разделе "Управление доступом на основе ролей[(RBAC)"](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Откройте окно браузера и введите URL-Администратор, чтобы открыть Skype для бизнеса Server панель управления.

3.  На панели навигации слева щелкните " **Топология**" и выберите пункт " **Доверенное приложение"**.

4.  На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).


## <a name="view-trusted-application-information"></a>Просмотр сведений о доверенном приложении

Сведения о доверенных приложениях можно просмотреть с помощью Windows PowerShell **командлета Get-CsTrustedApplication**. Этот командлет можно запустить либо из Skype для бизнеса Server Management Shell, либо из удаленного сеанса Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Просмотр доверенных приложений

Чтобы просмотреть все доверенные приложения, введите следующую команду в командной консоли Skype для бизнеса Server и нажмите клавишу ВВОД:
    
   **Get-CsConferenceDisclaimer**
    
   Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:
    
   Удостоверение: CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool: 487279971<br/>
   HomeServer : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com OwnerUrn : urn:application:helpdesk<br/>
   SipAddress: sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   Displayname:<br/>
   DisplayNumber:<br/>
   LineURI:<br/>
   PrimaryLanguage: 0<br/>
   SecondaryLanguages: {}<br/>
   EnterpriseVoiceEnabled: True<br/>
   ExUmEnabled: False<br/>
   Включено: true<br/>
    
   Дополнительные сведения см. в разделе [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).