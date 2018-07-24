---
title: Развертывание нескольких локальных лесов для системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.
ms.openlocfilehash: 35a6d5401b2e554cbfaa1e97c42e9a88bc3558ed
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966061"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Развертывание нескольких локальных лесов для системы комнат Skype
 
В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.
  
> [!NOTE]
> Для развертывания в нескольких лесах, система комнаты Скайп требуется Exchange Server 2013 CU6 выпущен 26 августа 2014 г. Избегайте повторное использование существующего почтового ящика для помещения Скайп системы. Использовать новый (удаление старых почтовых ящиков и повторное создание) почтового ящика ресурса для помещения Скайп системы. Чтобы восстановить собраний, потеряны при удалении почтового ящика, видеть [подключение или восстановление удаленного почтового ящика](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Создав почтовый ящик, вы можете настроить его с помощью командлетов Set-CalendarProcessing. Обратитесь к шаги с 3 по 6 в разделе локальные развертывания одного леса для получения дополнительных сведений. После создания почтового ящика Exchange ресурсов для системы Скайп помещения, включить учетную запись для Скайп для бизнеса, выполнив действия в Включение Скайп комнаты системных учетных записей для Скайп для бизнеса в разделе локальные развертывания одного леса.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Вариант 1. Создание нового почтового ящика ресурсов

Для развертывания в среде с несколькими лесами Скайп комнаты системы:
  
1. Создайте связанного пользователя (LinkedRoomTest) в Active Directory (Authentication Forest).
    
2. Выполните следующие команды в командной консоли Exchange Server:
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Вариант 2: Изменение существующего почтового ящика помещения к почтовому ящику (связанные) ресурсов системы Скайп комнаты

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


