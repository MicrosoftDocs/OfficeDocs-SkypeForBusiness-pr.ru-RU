---
title: Изменение простых URL-адресов после миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype для бизнеса Server поддерживает простые URL-адреса.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753909"
---
# <a name="change-simple-urls-after-migration"></a>Изменение простых URL-адресов после миграции

Skype для бизнеса Server поддерживает три простых URL-адреса:
  
- **Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute. 
    
- **Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information. 
    
- **Администратор** обеспечивает быстрый доступ к панели управления Skype для бизнеса Server. Этот URL-адрес используется внутри организации. 
    
После перехода на Skype для бизнеса Server необходимо знать, как это изменение влияет на записи DNS и сертификаты для простых URL-адресов. Если устаревший директор Skype для бизнеса Server не используется в топологии, изменения простых URL-адресов не требуются. Если директор Skype для бизнеса Server удален из топологии после миграции, DNS-записи простых URL-адресов необходимо обновить, чтобы указать один из пулов Skype для бизнеса Server. Однако при любом изменении простого URL-адреса вам необходимо выполнить командлет Enable-CsComputer на каждом Директоре и сервере переднего плана, чтобы зарегистрировать это изменение.

## <a name="to-update-the-meet-simple-url"></a>Обновление простого URL-адреса собраний

1. В построителе топологий щелкните правой кнопкой мыши верхний узел в **Skype для бизнеса Server**, а затем выберите команду **изменить свойства**.
    
2. В левой области выберите **простые URL** -адреса, а затем в разделе URL **-адреса собраний:** выберите URL-адрес соответствия, а затем щелкните **изменить URL-адрес**.
    
3. Задайте для URL-адреса требуемое значение и нажмите кнопку **ОК**, чтобы сохранить изменения. 
    
## <a name="to-update-the-admin-simple-url"></a>Обновление простого URL-адреса администратора

1. В построителе топологий щелкните правой кнопкой мыши верхний узел в **Skype для бизнеса Server**, а затем выберите команду **изменить свойства**.
    
2. Выберите **простые URL-адреса** в левой области, а затем в поле **URL-адрес административного доступа** введите простой URL-адрес, который требуется использовать для административного доступа к панели управления Skype для бизнеса Server, а затем нажмите кнопку **ОК**.
    
   > [!TIP]
   > Рекомендуется использовать самый простой URL-адрес для административного доступа. Самый простой вариант — https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>См. также

[Требования DNS для простых URL-адресов в Skype для бизнеса Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
