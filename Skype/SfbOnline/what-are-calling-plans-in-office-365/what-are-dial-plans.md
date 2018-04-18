---
title: What are dial plans?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what type of dial calling plans (PSTN Calling dial plans) are available with Office 365 and how to choose one for your organization.  '
search.appverid:
- MED150
- MOE150
ms.openlocfilehash: c24727dec0a9d938b3b0e40ef6f47501944e70e1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-dial-plans"></a>What are dial plans?

[] Абонентская группа  это именованный набор правил нормализации, который преобразует номера телефонов отдельных пользователей в альтернативный формат (обычно E.164) для авторизации и маршрутизации звонков.
  
A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format. The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.
  
## <a name="tenant-dial-plan-scope"></a>Область действия абонентской группы для клиента

Область действия абонентской группы определяет уровень иерархии, на котором возможно применение данной абонентской группы. The scopes are different than in a Skype for Business Server 2015 on-premises deployment. Клиенты получают соответствующие абонентские группы с помощью параметров подготовки, которые предоставляются автоматически при входе клиентов в Skype для бизнеса Online. Как администратор вы можете назначать уровни действия абонентских групп и управлять ими с помощью удаленной оболочки PowerShell.
  
In Skype for Business Online, there are two types of dial plans - service scoped and tenant (which is for your organization) scoped. A service scoped dial plan is defined for every country/region where the Office 365 Phone System is available. Each user is automatically assigned the service country dial plan that matches the Office 365 Usage Location assigned to the user. You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan. As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan. Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.
  
Абонентские группы на основе клиентов можно дополнительно разбить на две области действия: область действия клиента и область действия пользователя. Если клиент определяет и назначает абонентскую группу на уровне пользователя, для этого пользователя подготавливается эффективная абонентская группа с учетом абонентской группы страны обслуживания и назначенной абонентской группы пользователя. Если клиент определяет абонентскую группу с областью действия клиента, но не назначает абонентскую группу на уровне пользователя, для этого пользователя подготавливается эффективная абонентская группа с учетом абонентской группы страны обслуживания и абонентской группы клиента.
  
Ниже приведена модель наследования абонентских групп в Skype для бизнеса Online.
  
![How dial plans are inherited in Skype for Business Online.](../images/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
Ниже перечислены возможные эффективные абонентские группы.
  
 **Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their Office 365 Usage Location.
  
 **Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
 **Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their Office 365 Usage Location.
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="planning-for-tenant-dial-plans"></a>Планирование абонентских групп клиента

Для планирования настраиваемых абонентских групп выполните следующие шаги.
  
- **Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience. Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.
    
- **Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both. User scoped dial plans are needed if users have different local dialing requirements.
    
- **Шаг 3.** Определите допустимые шаблоны номеров для каждой из необходимых абонентских групп. Требуются только те шаблоны, которые не заданы в абонентских группах страны обслуживания.
    
- **Шаг 4.** Разработайте схему именования абонентских групп на уровне организации. Использование стандартной схемы именования обеспечивает согласованность работы, а также упрощает обслуживание и обновление системы.
    
The [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) has additional resources and partners that can assist you with implementing tenant dial plans.
  
## <a name="creating-your-new-tenant-dial-plan"></a>Создание абонентской группы клиента

При создании абонентской группы следует указать необходимые сведения.
  
### <a name="name-and-simple-name"></a>Имя и простое имя

For user dial plans, you should specify a descriptive name that identifies to the users the dial plan will be assigned. The dial plan Simple Name is prepopulated with a string that is derived from the dial plan name. Поле "Простое имя" доступно для редактирования, что позволяет создать для абонентских групп информативное соглашение об именовании. The Simple Name value cannot be empty and must be unique. Рекомендуется разработать соглашение об именовании для всей организации и последовательно применять его для всех сайтов и пользователей.
  
### <a name="description"></a>Описание

Рекомендуется указать общеупотребительное и узнаваемое название географического расположения или группы пользователей, к которому будет применена соответствующая абонентская группа.
  
### <a name="external-access-prefix"></a>Префикс для внешнего доступа

> [!CAUTION]
> Префикс внешнего доступа на данный момент не поддерживается. 
  
Если пользователям нужно набирать одну или несколько начальных цифр (например, цифру 9) для доступа к внешней линии, можно указать префикс для внешнего доступа длиной до четырех символов (допускаются символы #, * и 0-9).
  
> [!NOTE]
> В случае указания префикса создавать дополнительное правило нормализации для него не требуется. 
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.
  
## <a name="normalization-rules"></a>Правила нормализации

Правила нормализации определяют, как преобразуются номера телефонов, указанные в разных форматах. Одна и та же строка номера может быть интерпретирована и преобразована по-разному, в зависимости от языкового стандарта, который применяется к набравшему ее пользователю. Правила нормализации могут потребоваться, если пользователям нужно набирать сокращенные внутренние или внешние номера.
  
One or more normalization rules must be assigned to the dial plan. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth. If a match is made, that rule is used and there is no effort to match any other rules that are defined. There can be a maximum of 25 normalization rules in a given tenant dial plan.
  
### <a name="determining-the-required-normalization-rules"></a>Определение необходимых правил нормализации

Так как любая абонентская группа клиента фактически объединяется с абонентской группой страны обслуживания для заданного пользователя, то для определения необходимых правил нормализации абонентской группы клиента, скорее всего, потребуется оценка правил нормализации абонентской группы для страны обслуживания. Для этого можно воспользоваться командлетом **Get-CsEffectiveTenantDialPlan**. Командлет использует удостоверение пользователя в качестве входного параметра и возвращает все правила нормализации, которые применяются к этому пользователю.
  
### <a name="creating-normalization-rules"></a>Создание правил нормализации

Правила нормализации используют регулярные выражения платформы .NET Framework для указания шаблонов числовых соответствий, которые используются сервером для преобразования набираемых строк в формат E.164 для обратного преобразования номеров. Для создания правил нормализации можно указать регулярное выражение для проверки соответствия, и при обнаружении соответствия будет выполнено преобразование. После окончания настройки можно ввести тестовый номер, чтобы проверить работу правил нормализации.
  
For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.
  
### <a name="sample-normalization-rules"></a>Примеры правил нормализации

В следующей таблице приведены примеры правил нормализации, написанных в виде регулярных выражений .NET Framework. Эти примеры приведены только для справки, поэтому не следует рассматривать их в качестве рекомендаций по созданию правил.
  
 **Normalization rules using .NET Framework regular expressions**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Имя правила** <br/> |**Описание** <br/> |**Шаблон номеров** <br/> |**Преобразование** <br/> |**Пример** <br/> |
|4digitExtension  <br/> |Преобразует расширения из четырех цифр.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 преобразуется в +14255550100  <br/> |
|5digitExtension  <br/> |Преобразует расширения из пяти цифр.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 преобразуется в +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Преобразует номера из семи цифр в местные номера Редмонда.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 преобразуется в +14255550100  <br/>|
|RedmondOperator  <br/> |Преобразует 0 в номер оператора Редмонда.  <br/> |^0$  <br/> |+14255550100  <br/> |0 преобразуется в +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Преобразует номера с внутрисетевым префиксом (6) и кодом Редмонда (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 преобразуется в +14255550100  <br/> |
|5digitRange  <br/> |Преобразует расширения из пяти цифр, которые начинаются с цифры из диапазона от трех до семи включительно.  <br/> |^([3-7]\\d{4})$  <br/> |+142570$1  <br/> |54567 преобразуется в +14255554567  <br/> |
|PrefixAdded  <br/> |Добавляет префикс страны перед номером из девяти цифр с ограничениями для первой и третьей цифр.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 преобразуется в 14255554567  <br/> |
|NoTranslation  <br/> |Соответствует пяти цифрам, но преобразование не выполняется.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 преобразуется в 34567  <br/> |
   
 **Абонентская группа Редмонда основана на приведенных выше правилах нормализации.**
  
В следующей таблице показан пример абонентской группы для города Редмонда (штат Вашингтон, США) на основе правил нормализации из предыдущей таблицы.
|:-----| |**Redmond dial plan** <br/> | |5digitExtension <br/> | |7digitcallingRedmond <br/> | |RedmondSitePrefix <br/> | |RedmondOperator <br/> |
   
> [!NOTE]
> Названия правил нормализации из предыдущей таблицы не содержат пробелов, но вы можете использовать пробелы в названиях своих правил. Например, первое правило в таблице могло называться 5 digit extension или 5-digit Extension (добавочный номер из 5 цифр). 
  
## <a name="related-topics"></a>See also
[Создание абонентских групп и управление ими](create-and-manage-dial-plans.md)

[Лицензирование надстроек Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

[Общие вопросы по передаче номеров телефонов](transferring-phone-numbers-common-questions.md)

[Типы номеров телефонов, используемые в планах звонков](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Управление номерами телефонов организации](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Условия и положения, распространяющиеся на экстренные вызовы](emergency-calling-terms-and-conditions.md)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 