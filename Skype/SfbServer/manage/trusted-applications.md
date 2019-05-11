---
title: Управление доверенными приложениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Доверенное приложение — это приложение, на основании Microsoft Unified Communications управляемых API (UCMA) 3.0 Core SDK, который является доверенным Скайп для Business Server.
ms.openlocfilehash: 0f483cc0a1a3a9e7dad881fc40819a9c27dacdec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911870"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>Управление доверенными приложениями в Скайп Business Server

*Доверенное приложение* — это приложение, на основании Microsoft Unified Communications управляемых API (UCMA) 3.0 Core SDK, который является доверенным Скайп для Business Server. Для получения дополнительных сведений о приложениях UCMA документации «единой Communications управляемых API 3.0 Core SDK» в http://go.microsoft.com/fwlink/p/?linkId=210320.

Для успешной публикации, включения или отключения топологии при добавлении или удалении роль сервера, необходимо войти в систему как пользователь, являющийся членом группы RTCUniversalServerAdmins и "Администраторы домена". 

Используйте эту статью, чтобы узнать, как для настройки нового сервера доверенных приложений, Просмотр списка доверенных приложений и просмотра сведений о доверенном приложении. 

## <a name="configure-a-new-trusted-application-server"></a>Настройка нового сервера доверенных приложений

1.  Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.

2.  Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для Business Server Topology Builder**.

3.  Выберите **загрузить топологию из существующего развертывания**и нажмите кнопку **ОК**.

4.  В диалоговом окне **Save Topology As** щелкните Topology Builder файл, который требуется использовать и нажмите кнопку **Сохранить**.

5.  В левой области щелкните правой кнопкой мыши **серверы доверенных приложений**и нажмите кнопку **Создать пул доверенных приложений**.

6.  Введите **Полное доменное имя пула** пула доверенных приложений, выберите, будет ли он будет одним или несколькими серверами и нажмите кнопку **Далее**.

7.  На странице **Выбор следующего прыжка** в списке выберите Скайп для пула переднего плана Business Server.

8.  Нажмите **Готово**.

9.  Выберите верхний узел **Скайп для Business Server**и затем в меню **действия** щелкните **Опубликовать топологию**.
    
    Следует, **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.


## <a name="view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

Скайп для панели управления Business Server можно использовать для просмотра списка доверенных приложений, которые развернуты в вашей Скайп среды Business Server. Доверенное приложение — это приложение, на основании Microsoft Unified Communications управляемых API (UCMA) 3.0 Core SDK, который является доверенным Скайп для Business Server. В списке ниже приведен этого отношения доверия:

  - К доверенным приложениям не требуется проходить проверки подлинности Скайп для Business Server.

  - К доверенным приложениям не применяется регулирование Скайп для Business Server для транзакций SIP, подключений или исходящих вызовов по протоколу (VoIP).

  - Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.

  - Доверенные приложения устойчивы и надежны.

В Скайп для панели управления Business Server можно видеть имя приложения, пул, в котором оно выполняется и порт, которые они используют.


### <a name="to-view-a-list-of-trusted-applications"></a>Просмотр списка доверенных приложений

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator. Для получения дополнительных сведений о предопределенные административные роли, доступные в Скайп для Business Server см [управления доступом на основе ролей (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.

3.  В левой панели навигации щелкните **Топология**и нажмите кнопку **Доверенных приложений**.

4.  На странице **Доверенное приложение** щелкните заголовок столбца, чтобы отсортировать приложения при необходимости.


## <a name="view-trusted-application-information"></a>Просмотр сведений о доверенном приложении

Можно просмотреть сведения о доверенных приложений с помощью командлета **Get-CsTrustedApplication** и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>Просмотр доверенных приложений

Для просмотра всех доверенных приложений, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:
    
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
    
   Дополнительные сведения см [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).
