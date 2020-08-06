---
title: Capturar dados de eventos do gatilho de logon | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
author: rothja
ms.author: jroth
ms.openlocfilehash: b11323702d7468d07783b4d1c763dba691479d9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582897"
---
# <a name="capture-logon-trigger-event-data"></a><span data-ttu-id="5916e-102">Capturar dados de eventos do gatilho de logon</span><span class="sxs-lookup"><span data-stu-id="5916e-102">Capture Logon Trigger Event Data</span></span>
  <span data-ttu-id="5916e-103">Para capturar dados XML sobre eventos LOGON para uso nos gatilhos de logon, use a função [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5916e-103">To capture XML data about LOGON events for use inside logon triggers, use the [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) function.</span></span> <span data-ttu-id="5916e-104">O evento LOGON retorna o seguinte esquema de dados de evento:</span><span class="sxs-lookup"><span data-stu-id="5916e-104">The LOGON event returns the following event data schema:</span></span>  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 <span data-ttu-id="5916e-105">Contém `LOGON`.</span><span class="sxs-lookup"><span data-stu-id="5916e-105">Contains `LOGON`.</span></span>  
  
 `<PostTime>`  
 <span data-ttu-id="5916e-106">Contém a hora em que foi solicitado o estabelecimento de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="5916e-106">Contains the time when a session is requested to be established.</span></span>  
  
 `<SID>`  
 <span data-ttu-id="5916e-107">Contém o fluxo binário codificado de base 64 do número de identificação de segurança (SID) do nome de logon especificado.</span><span class="sxs-lookup"><span data-stu-id="5916e-107">Contains the base 64-encoded binary stream of the security identification number (SID) for the specified login name.</span></span>  
  
 `<ClientHost>`  
 <span data-ttu-id="5916e-108">Contém o nome do host do cliente de onde é feita a conexão.</span><span class="sxs-lookup"><span data-stu-id="5916e-108">Contains the host name of the client from where the connection is made.</span></span> <span data-ttu-id="5916e-109">O valor será '`<local_machine>`' se o nome do cliente e do servidor forem idênticos.</span><span class="sxs-lookup"><span data-stu-id="5916e-109">The value is '`<local_machine>`' if the client and server name are the same.</span></span> <span data-ttu-id="5916e-110">Caso contrário, o valor é o endereço de IP do cliente.</span><span class="sxs-lookup"><span data-stu-id="5916e-110">Otherwise, the value is the IP address of the client.</span></span>  
  
 `<IsPooled>`  
 <span data-ttu-id="5916e-111">Será `1` se a conexão for reutilizada por meio de pool de conexões.</span><span class="sxs-lookup"><span data-stu-id="5916e-111">Is `1` if the connection is reused by using connection pooling.</span></span> <span data-ttu-id="5916e-112">Caso contrário, o valor é `0`.</span><span class="sxs-lookup"><span data-stu-id="5916e-112">Otherwise, the value is `0`.</span></span>  
  
  
