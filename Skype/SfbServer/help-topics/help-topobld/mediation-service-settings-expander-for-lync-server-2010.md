---
title: Расширитель настроек службы сервера-посредника для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: Свойства службы посредника можно изменить, определив следующие свойства
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215110"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="4287b-103">Расширитель настроек службы сервера-посредника для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4287b-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="4287b-104">Свойства службы посредника можно изменить, определив следующие свойства</span><span class="sxs-lookup"><span data-stu-id="4287b-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="4287b-p101">**Порты прослушивания**. Определите порт **TLS**, который будет прослушиваться службой посредника. По умолчанию значением порта является TCP 5067 по TLS</span><span class="sxs-lookup"><span data-stu-id="4287b-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="4287b-p102">Дополнительно можно определить значение порта **TCP**. По умолчанию используется значение TCP 5068.</span><span class="sxs-lookup"><span data-stu-id="4287b-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4287b-p103">Значение порта TCP включается путем выбора параметра **Включить порт TCP**. Необходимо ознакомиться с документацией по шлюзу выхода в телефонную сеть общего пользования (ТСОП) или офисной АТС с поддержкой IP-телефонии, чтобы узнать о требованиях к настройке портов для связи со службой посредника.</span><span class="sxs-lookup"><span data-stu-id="4287b-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="4287b-111">**Включение порта TCP** необходимо для определения значения порта для связи по TCP с шлюзом ТСОП или офисной АТС с поддержкой IP-телефонии.</span><span class="sxs-lookup"><span data-stu-id="4287b-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="4287b-112">Указание назначенных и существующих значений **Линия связи** (то есть линия связи протокола SIP), **Шлюз** (шлюз ТСОП или IP-АТС) и **Сайт** (сайт, настроенный для линии связи и шлюза).</span><span class="sxs-lookup"><span data-stu-id="4287b-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="4287b-p104">Выберите линию связи, шлюз и сайт, а затем щелкните элемент **По умолчанию**, чтобы установить выбранные значения в качестве используемых по умолчанию для данного сервера-посредника. Выберите текущее значение по умолчанию и щелкните элемент **Отменить по умолчанию**, чтобы отменить использование этого значения по умолчанию. После этого выберите новое значение по умолчанию и щелкните элемент **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="4287b-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="4287b-116">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="4287b-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="4287b-117">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="4287b-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="4287b-118">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="4287b-118">**Help** Displays this help screen.</span></span>
  

