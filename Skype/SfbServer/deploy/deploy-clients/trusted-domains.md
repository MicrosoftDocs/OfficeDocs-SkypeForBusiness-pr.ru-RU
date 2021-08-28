---
title: Skype Доверенные домены системы номеров
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Ознакомьтесь с этой темой, чтобы узнать, как настроить доверенные домены для Skype и Skype для бизнеса.
ms.openlocfilehash: fae745d1380e8d75d88e446275d7073e92ae5632
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583273"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Доверенные домены системы номеров
 
Ознакомьтесь с этой темой, чтобы узнать, как настроить доверенные домены для Skype и Skype для бизнеса.
  
## <a name="trusted-domains"></a>Доверенные домены

Клиент Skype для бизнеса отображает диалоговое окно, которое позволяет пользователям принимать сертификат из Skype для бизнеса Server, если домен SIP входной учетной записи пользователя отличается от имени, представленного в имени Subject или Subject Alt в сертификате. Если сертификат, настроенный для Skype для бизнеса Server в организации, не имеет доменного имени SIP учетной записи системы номеров Skype в Subject или Subject Alt Name, необходимо настроить эти домены, представленные в сертификате под ключом реестра доверенных доменов на консоли Skype консольной машине системы номеров. Руководство Skype системы номеров Skype руководство администратора системы номеров объясняет, как и где добавлять доверенные домены в Skype для бизнеса клиенте. 
  
Например, предположим, что сертификаты, настроенные на Skype для бизнеса Server, имеют имя субъекта и субъекта Alt "CONTOSO. LOCAL" и один из доменов SIP, присвоенных пользователю для Skype системы регистрации номеров, является "confrm1@contoso.net". Поскольку contoso.net в сертификате нет, на компьютере Skype Room System необходимо настроить "contoso.local" в качестве надежного домена в реестре, как поясняется в руководстве Skype-изготовителя системы номеров Skype администратора системы номеров. 
  

