---
title: Настройка Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Инструкции по настройке Azure AD Connect в гибридной среде.
ms.openlocfilehash: 7a0c458692da1381f2ed3f52dfef8c1d360d74e2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221473"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Настройка Azure AD Connect для Teams и Skype для бизнеса
 
Организации с локальной службой Skype для бизнеса Server (или Lync Server) и планирую использовать Teams или Skype для бизнеса Online, должны настроить Azure AD Connect для синхронизации локального каталога с Microsoft 365 или Office 365, как описано в этом документе.  К ним относятся организации, которые перемещаются непосредственно из локальной сети Skype для бизнеса в Teams. В частности, организации с локальной службой Skype для бизнеса должны обеспечить синхронизацию надлежащих атрибутов msRTCSIP в Azure AD. 

> [!NOTE]
> Существующим пользователям Teams, у которых также есть локальная служба Skype для бизнеса, потребуется перенести локальную учетную запись Skype для бизнеса в облако, чтобы получить полный набор функций (например, возможность взаимодействовать с пользователями Skype для бизнеса или общаться с пользователями в федеративных организациях). Даже если пользователь будет использовать только Teams, эта сетевая учетная запись Skype для бизнеса необходима инфраструктуре для предоставления дополнительных функций.  Для этой миграции необходимо убедиться, что служба Azure AD Connect настроена должным образом, чтобы можно было включить гибридную среду.
 

## <a name="background-information"></a>Базовые сведения

Azure Active Directory Connect обеспечивает постоянное синхронизацию локальной службы Active Directory с Microsoft 365 или Office 365.  Локальный каталог остается полномочным источником удостоверений, а изменения в локальной среде синхронизируются со службой Azure AD. Дополнительные сведения см. в [синхронизированной службе Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)  Даже если вы перемещаете не всех пользователей из локальной сети в облако, все пользователи, которые используют Teams, локальное приложение Skype для бизнеса или Skype для бизнеса Online, должны быть синхронизированы с локальной службой Azure AD, чтобы обеспечить взаимодействие между локальной и сетевой пользователями. *Пользователи в организации будут представлены в локальном и сетевом каталогах.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Настройка Azure AD для работы со Skype для бизнеса Server 

Независимо от того, имеется ли у вас один локальной лес Active Directory или несколько лесов, Azure AD Connect можно использовать в различных поддерживаемых topologies, как описано в [topologies for Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)  С точки зрения Skype для бизнеса Server существует три основных варианта. 

1. Один лес, содержащий полномочные удостоверения пользователей и Skype для бизнеса Server. 

2. Несколько лесов, в одном из которых размещается Skype для бизнеса Server, а также один или несколько других лесов, содержащих полномочные удостоверения пользователей (лесов учетных записей). 

3. Несколько развертываний Skype для бизнеса Server в нескольких лесах. При условии, что выполнены определенные требования, организации могут объединить эти развертывания в одну организацию Microsoft 365 или Office 365.

### <a name="single-forest"></a>Один лес 

Если все учетные записи пользователей и Skype для бизнеса размещены в одном лесу, необходимо убедиться, что настроено средство Azure AD Connect, чтобы синхронизировать пользователей из этого леса с Azure AD.  Несмотря на то что мастер установки Azure AD Connect содержит множество параметров, подходящие атрибуты будут автоматически синхронизированы с Azure Active Directory. Клиентам не рекомендуется изменять встроенные правила синхронизации и(или) соединители, которые управляют конфигурацией (что невозможно в мастере установки).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Несколько лесов с одним развертыванием Skype для бизнеса 

Этот сценарий часто называют топологией леса ресурсов. Полномочные удостоверения пользователей размещаются в одном или нескольких лесах учетных записей, а Skype для бизнеса развертывается в отдельном лесу ресурсов (в котором также могут размещаться полномочные удостоверения пользователей). В общем случае полномочные удостоверения пользователей Skype для бизнеса могут находиться в том же лесу, что и Skype для бизнеса Server, и/или в другом лесу при соблюдении указанных ниже условий. 

- Пользователи с полномочными удостоверениями из лесов учетных записей предоставлены в лесу ресурсов (где развернута служба Skype для бизнеса Server) как отключенные объекты пользователей, а атрибут msRTCSIP-OriginatorSID в лесу ресурсов совпадает с SID в лесу учетных записей. Дополнительные сведения см. в подстройке "Настройка среды с [несколькими лесами для гибридной среды Skype для бизнеса".](configure-a-multi-forest-environment-for-hybrid.md)

- Лес ресурсов, в котором размещается Skype для бизнеса Server, доверяет лесам учетных записей.  

- Все соответствующие объекты пользователей и атрибуты для удостоверений (из лесов учетных записей) и Skype для бизнеса (из леса ресурсов) синхронизируются в Azure AD с правильными значениями через Azure AD Connect.  

 Чтобы обеспечить правильную синхронизацию объектов и [](configure-a-multi-forest-environment-for-hybrid.md)атрибутов с Azure AD в локальном сценарии с несколькими лесами, корпорация Майкрософт настоятельно рекомендует использовать Azure AD Connect для синхронизации из всех лесов, включив учетные записи пользователей, и леса, включаемого в Skype для бизнеса.  Если выполняется синхронизация из всех лесов, далее необходимо настроить Azure AD Connect для объединения этих удостоверений и их синхронизации в Azure AD. Средство Azure AD Connect предназначено для работы в этом сценарии, а в мастере установки предусмотрен встроенный параметр для его настройки, включая настройку привязок для объединения удостоверений.  Выберите следующее: удостоверения пользователей существуют в нескольких каталогах. Соответствие с помощью атрибутов --> ObjectSID и msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Несколько развертываний Skype для бизнеса Server в нескольких лесах 

В этом сценарии существует несколько лесов, каждый из которых содержит Skype для бизнеса Server, и одна организация Microsoft 365 или Office 365.  Каждый лес, содержащий Skype для бизнеса Server, можно синхронизировать с Azure AD для этой организации с помощью AAD Connect. В любой момент для гибридной среды Skype для бизнеса может быть настроен только один лес. Перед включением гибридной системы в лесу все домены SIP из всех остальных лесов необходимо отключить с помощью [disable-csonlineSipDomain.](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) Дополнительные сведения о том, как консолидировать такую среду в Microsoft 365 или Office 365, см. в сведениях о консолидации облака для Teams и [Skype для бизнеса.](cloud-consolidation.md)

## <a name="general-requirements"></a>Общие требования 

Для служб Teams и Skype для бизнеса Online необходимо, чтобы правильные атрибуты Active Directory существовали и заполнялись в Azure AD.  Корпорация Майкрософт обычно синхронизирует все леса, содержащие удостоверения пользователей, а также все леса, содержащие Skype для бизнеса Server.

 Если удостоверения пользователей существуют в нескольких лесах, необходимо выполнить объединение с помощью Azure AD Connect. После этого Azure AD Connect автоматически синхронизирует правильные атрибуты, если вы не измените соединители или правила синхронизации в Azure AD Connect. 
  
If you do not synchronize from all forests that contain user identities and the Skype for Business Server deployment, you must still ensure the relevant identity and Skype for Business attributes are correctly populated into Azure AD for any user using Teams or Skype for Business (whether on-premises or online)--which will likely require additional on-premises directory synchronization. Дополнительные сведения см. в [синхронизации Azure AD Connect: атрибуты, синхронизированные с Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

В таких сценариях клиент обязан обеспечить правильную конфигурацию для заполнения атрибутов в Azure AD. Учитывайте следующее: 

- Использование нестандартной конфигурации для синхронизации с Azure AD рискованно, так как это может привести к неправильной настройке, которая может вызвать повреждение данных в сетевом каталоге.

- По мере развития продуктов корпорация Майкрософт продолжит проверять стандартные конфигурации синхронизации, в которых синхронизируются все соответствующие леса. Клиенты с пользовательскими конфигурациями синхронизации обязаны гарантировать, что их конфигурации доставляют правильные атрибуты и значения в Azure AD. 

## <a name="related-information"></a>Статьи по теме

- [Что такое гибридное удостоверение](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Синхронизация Azure AD Connect: понимание и настройка синхронизации](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Топологии Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Синхронизация Azure AD Connect: атрибуты, синхронизированные с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
