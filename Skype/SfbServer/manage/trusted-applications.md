---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Доверенным приложением является приложение на основе API управляемых единой связи (UCMA) 3.0 Core SDK, которому доверяют Skype для бизнеса Server.
ms.openlocfilehash: 4164f00b787ac8f234d13ba7c31e54c79cb1efd7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750168"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Управление доверенными приложениями в Skype для бизнеса Server

Доверенным *приложением* является приложение на основе API управляемых единой связи (UCMA) 3.0 Core SDK, которому доверяют Skype для бизнеса Server. Подробные сведения о приложениях UCMA см. в материале "Объединенные коммуникации управляемый API 3.0 Core SDK https://go.microsoft.com/fwlink/p/?linkId=210320 Documentation".

Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена". 

В этой статье вы узнаете, как настроить новый надежный сервер приложений, просмотреть список доверенных приложений и просмотреть доверенные сведения о приложениях. 

## <a name="configure-a-new-trusted-application-server"></a>Настройка нового доверенного сервера приложений

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Начните строитель топологии: нажмите кнопку **Начните,** щелкните Все **программы,** **нажмите кнопку Skype для бизнеса Server,** а затем нажмите кнопку Skype для бизнеса Server **Topology Builder**.

3.  Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.

4.  В **диалоговом окне Сохранить** топологию как диалоговое окно щелкните файл Topology Builder, который необходимо использовать, а затем нажмите **кнопку Сохранить**.

5.  В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.

6.  В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).

7.  На **следующей странице "Выберите переход"** из списка выберите Skype для бизнеса Server пула переднего конца.

8.  Нажмите кнопку **Готово**.

9.  Выберите верхний узел **Skype для бизнеса Server,** а затем из меню **Действия** нажмите **кнопку Опубликовать топологию**.
    
    Пул **доверенных приложений** должен был быть создан успешно и связан с правильным пулом переднего конца.


## <a name="view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

Панель управления Skype для бизнеса Server для просмотра списка доверенных приложений, развернутых в Skype для бизнеса Server среде. Доверенным приложением является приложение на основе API управляемых единой связи (UCMA) 3.0 Core SDK, которому доверяют Skype для бизнеса Server. В списке ниже приведены сведения об этом отношении доверия.

  - Доверенные приложения не оспариваются для проверки подлинности Skype для бизнеса Server.

  - Доверенные приложения не Skype для бизнеса Server для SIP-транзакций, подключений или исходяющих вызовов Голосовой связи через Интернет-протокол (VoIP).

  - Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.

  - Доверенные приложения устойчивы и надежны.

В панели Skype для бизнеса Server вы можете увидеть имя приложений, пул, в котором они работают, и порт, который они используют.


### <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

1.  Из учетной записи пользователя, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или роли CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании. Сведения о предопределеных административных ролях, доступных в Skype для бизнеса Server, см. в материале [Role-based access control (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3.  В левой панели навигации щелкните **Топология** и нажмите кнопку **Доверенные приложения**.

4.  На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).


## <a name="view-trusted-application-information"></a>Просмотр доверенных сведений о приложениях

Сведения о доверенных приложениях можно просматривать с помощью Windows PowerShell **и cmdlet Get-CsTrustedApplication.** Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Просмотр доверенных приложений

Чтобы просмотреть все доверенные приложения, введите следующую команду в командной Skype для бизнеса Server, а затем нажмите кнопку ENTER:
    
   **Get-CsConferenceDisclaimer**
    
   Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:
    
   Identity: CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litware,DC=com<br/>
   RegistrarPool : 487279971<br/>
   HomeServer: CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC Service,CN=Services, CN=Configuration,DC=litware,DC=com OwnerUrn: urn:application:helpdesk<br/>
   SipAddress : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com<br/>
   DisplayName:<br/>
   DisplayNumber:<br/>
   LineURI :<br/>
   PrimaryLanguage : 0<br/>
   SecondaryLanguages: {}<br/>
   EnterpriseVoiceEnabled : True<br/>
   ExUmEnabled : False<br/>
   Включено: True<br/>
    
   Дополнительные сведения см. в разделе [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).