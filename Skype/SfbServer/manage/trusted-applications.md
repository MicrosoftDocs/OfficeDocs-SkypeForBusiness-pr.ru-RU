---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Доверенного приложения это приложение на основе Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server.
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826279"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Управление доверенными приложениями в Skype для бизнеса Server

*Доверенного* приложения это приложение на основе Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server. Подробные сведения о приложениях UCMA см. в подразделе "Документация по unified Communications Managed API 3.0 Core SDK" по этой https://go.microsoft.com/fwlink/p/?linkId=210320 теме.

Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена". 

В этой статье вы узнаете, как настроить новый доверенный сервер приложений, просмотреть список доверенных приложений и просмотреть сведения о доверенных приложениях. 

## <a name="configure-a-new-trusted-application-server"></a>Настройка нового сервера доверенных приложений

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Запустите построитель топологий: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **Server"** и **"Построитель топологий Skype** для бизнеса Server".

3.  Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.

4.  В **диалоговом** окне "Сохранить топологию как" щелкните нужный файл построитель топологий и нажмите кнопку **"Сохранить".**

5.  В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.

6.  В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).

7.  On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.

8.  Нажмите кнопку **Готово**.

9.  Выберите верхний узел **Skype для бизнеса Server,** а затем в меню "Действия" щелкните **"Опубликовать топологию".** 
    
    Пул **доверенных приложений** должен быть успешно создан и связан с правильным пулом переднего входа.


## <a name="view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

Панель управления Skype для бизнеса Server можно использовать для просмотра списка доверенных приложений, развернутых в среде Skype для бизнеса Server. Доверенного приложения это приложение на основе Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK, которому доверяет Skype для бизнеса Server. В списке ниже приведены сведения об этом отношении доверия.

  - Доверенные приложения не будут подавлять заявки на проверку подлинности в Skype для бизнеса Server.

  - Skype для бизнеса Server не отрегулжимает доверенные приложения для транзакций SIP, подключений и исходяющих вызовов по протоколу VoIP.

  - Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.

  - Доверенные приложения устойчивы и надежны.

In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.


### <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

1.  Из учетной записи пользователя, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании. Подробные сведения о предопределеных административных ролях, доступных в Skype для бизнеса Server, см. в средстве управления доступом на основе [ролей (RBAC).](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3.  В левой панели навигации щелкните **"Топология"** и выберите **"Доверенного приложения".**

4.  На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).


## <a name="view-trusted-application-information"></a>Просмотр сведений о доверенных приложениях

Сведения о доверенных приложениях можно просмотреть с помощью Windows PowerShell и с помощью Windows PowerShell **Get-CsTrustedApplication.** Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Просмотр доверенных приложений

Чтобы просмотреть все доверенные приложения, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:
    
        Get-CsConferenceDisclaimer
    
   Эта команда возвращает сведения, подобные приведенным ниже, для каждого доверенного приложения:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   Дополнительные сведения см. в разделе [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
