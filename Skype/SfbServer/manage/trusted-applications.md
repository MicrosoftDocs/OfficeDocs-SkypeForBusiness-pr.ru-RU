---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Доверенное приложение — это приложение, основанное на Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Skype для бизнеса Server.
ms.openlocfilehash: c5c1a62440ebb98974cee5771c13cf0e5acc55c7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151229"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Управление доверенными приложениями в Skype для бизнеса Server

*Доверенное приложение* — это приложение, основанное на Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Skype для бизнеса Server. Подробные сведения о приложениях UCMA можно найти в https://go.microsoft.com/fwlink/p/?linkId=210320разделе "интегрированный API Managed Communications API 3,0".

Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена". 

Используйте эту статью, чтобы узнать, как настроить новый сервер доверенных приложений, просмотреть список доверенных приложений и просмотреть сведения о доверенных приложениях. 

## <a name="configure-a-new-trusted-application-server"></a>Настройка нового сервера доверенных приложений

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Skype для бизнеса Server**и **Построитель топологий Skype для бизнеса Server**.

3.  Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.

4.  В диалоговом окне **Сохранить топологию как** выберите нужный файл в построителе топологий, а затем нажмите кнопку **сохранить**.

5.  В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.

6.  В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).

7.  На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Skype для бизнеса Server.

8.  Нажмите кнопку **Готово**.

9.  Выберите верхний узел в **Skype для бизнеса Server**, а затем в меню **действия** выберите команду **опубликовать топологию**.
    
    **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.


## <a name="view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

Вы можете использовать панель управления Skype для бизнеса Server для просмотра списка доверенных приложений, развернутых в среде Skype для бизнеса Server. Доверенное приложение — это приложение, основанное на Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Skype для бизнеса Server. В списке ниже приведены сведения об этом отношении доверия.

  - Доверенные приложения не вызывают проверку подлинности в Skype для бизнеса Server.

  - Доверенные приложения не регулируются Skype для бизнеса Server для транзакций SIP, подключений или исходящих звонков по протоколу VoIP.

  - Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.

  - Доверенные приложения устойчивы и надежны.

В панели управления Skype для бизнеса Server можно просмотреть имена приложений, пула, в котором они выполняются, и порт, который они используют.


### <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

1.  Из учетной записи пользователя, назначенной для роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании. Подробные сведения о предопределенных административных ролях, доступных в Skype для бизнеса Server, представлены в разделе [Управление доступом на основе ролей (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.

3.  В левой панели навигации щелкните **топология**, а затем выберите **доверенное приложение**.

4.  На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).


## <a name="view-trusted-application-information"></a>Просмотр сведений о доверенном приложении

Сведения о доверенных приложениях можно просмотреть с помощью Windows PowerShell и командлета **Get – кструстедаппликатион** . Этот командлет можно запустить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Просмотр доверенных приложений

Чтобы просмотреть все доверенные приложения, введите следующую команду в командной консоли Skype для бизнеса Server, а затем нажмите клавишу ВВОД:
    
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
