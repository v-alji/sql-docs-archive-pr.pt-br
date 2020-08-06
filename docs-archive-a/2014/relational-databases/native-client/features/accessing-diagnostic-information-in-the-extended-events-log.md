---
title: Acessando informações de diagnóstico no log de eventos estendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: aaa180c2-5e1a-4534-a125-507c647186ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 5148683d464f06e8a4f52cc924baaacac9102b12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679922"
---
# <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="08228-102">Acessar informações de diagnóstico nos logs de eventos estendidos</span><span class="sxs-lookup"><span data-stu-id="08228-102">Accessing Diagnostic Information in the Extended Events Log</span></span>
  <span data-ttu-id="08228-103">A partir do [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e o rastreamento do acesso a dados ([Rastreamento do Acesso a Dados](https://go.microsoft.com/fwlink/?LinkId=125805)) foram atualizados para facilitar a obtenção de informações de diagnóstico sobre falhas de conexão do buffer de anéis de conectividade e informações de desempenho de aplicativo do registro de eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="08228-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data access tracing ([Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805)) have been updated to make it easier to get diagnostic information about connection failures from the connectivity ring buffer and application performance information from the extended events log.</span></span>  
  
 <span data-ttu-id="08228-104">Para obter mais informações sobre como ler o log de eventos estendidos, consulte [View Event Session Data](../../../database-engine/view-event-session-data.md).</span><span class="sxs-lookup"><span data-stu-id="08228-104">For information about reading the extended events log, see [View Event Session Data](../../../database-engine/view-event-session-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08228-105">Este recurso é destinado somente para finalidades de solucionar problemas e realizar diagnóstico, e pode não ser adequado para auditoria ou propósitos de segurança.</span><span class="sxs-lookup"><span data-stu-id="08228-105">This feature is intended only for troubleshooting and diagnostic purposes and may not be suitable for auditing or security purposes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08228-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="08228-106">Remarks</span></span>  
 <span data-ttu-id="08228-107">Para operações de conexão, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client enviará uma ID conexão de cliente.</span><span class="sxs-lookup"><span data-stu-id="08228-107">For connection operations, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will send a client connection ID.</span></span> <span data-ttu-id="08228-108">Se a conexão falhar, você poderá acessar o buffer de anéis de conectividade ([solução de problemas de conectividade no SQL Server 2008 com o buffer de anéis de conectividade](https://go.microsoft.com/fwlink/?LinkId=207752)) e localizar o `ClientConnectionID` campo e obter informações de diagnóstico sobre a falha de conexão.</span><span class="sxs-lookup"><span data-stu-id="08228-108">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](https://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="08228-109">As IDs de conexão de cliente estarão registradas no buffer de anéis se um erro ocorrer.</span><span class="sxs-lookup"><span data-stu-id="08228-109">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="08228-110">(Se uma conexão falhar antes de enviar o pacote anterior ao logon, uma ID conexão de cliente não será gerada.) A ID de conexão de cliente é um GUID de 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="08228-110">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="08228-111">Você também poderá localizar a ID de conexão de cliente no destino de saída dos eventos estendidos, se a ação de `client_connection_id` for adicionada a eventos em uma sessão de eventos estendida.</span><span class="sxs-lookup"><span data-stu-id="08228-111">You can also find the client connection ID in the extended events output target, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="08228-112">Você pode habilitar o rastreamento de acesso a dados e executar novamente o comando de conexão e observar o campo `ClientConnectionID` no rastreamento de acesso a dados para uma operação com falha, se precisar de assistência de diagnóstico adicional.</span><span class="sxs-lookup"><span data-stu-id="08228-112">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace for a failed operation, if you need further diagnostic assistance.</span></span>  
  
 <span data-ttu-id="08228-113">Se você estiver usando o ODBC no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e uma conexão for realizada com sucesso, poderá obter a ID de conexão do cliente usando o `SQL_COPT_SS_CLIENT_CONNECTION_ID` atributo com [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="08228-113">If you are using ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and a connection succeeds, you can get the client connection ID by using the `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribute with [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span></span>  
  
 <span data-ttu-id="08228-114">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client também envia uma ID de atividade específica de thread.</span><span class="sxs-lookup"><span data-stu-id="08228-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client also sends a thread-specific activity ID.</span></span> <span data-ttu-id="08228-115">A ID da atividade será capturada nas sessões de eventos estendidas se as sessões forem iniciadas com a opção de TRACK_CAUSAILITY habilitada.</span><span class="sxs-lookup"><span data-stu-id="08228-115">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="08228-116">Para problemas de desempenho com uma conexão ativa, você poderá obter a ID de atividade do rastreamento de acesso a dados do cliente (campo `ActivityID`) e, em seguida, localizar a ID de atividade nas saídas dos eventos estendidos.</span><span class="sxs-lookup"><span data-stu-id="08228-116">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="08228-117">A ID de atividade nos eventos estendidos é um GUID de 16 bytes (não o mesmo GUID para a ID de conexão de cliente) anexado a um número de sequência de quatro bytes.</span><span class="sxs-lookup"><span data-stu-id="08228-117">The activity ID in the extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="08228-118">O número de sequência representa a ordem de uma solicitação dentro de um thread e indica a ordenação relativa de lote e as instruções RPC para o thread.</span><span class="sxs-lookup"><span data-stu-id="08228-118">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="08228-119">O `ActivityID` é enviado opcionalmente para instruções de lote do SQL e solicitações do RPC quando o rastreamento de acesso a dados estiver habilitado e o 18º bit na palavra de configuração de rastreamento de acesso a dados estiver ativado (ON).</span><span class="sxs-lookup"><span data-stu-id="08228-119">The `ActivityID` is optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="08228-120">Veja a seguir um exemplo que usa o [!INCLUDE[tsql](../../../includes/tsql-md.md)] para iniciar uma sessão de eventos estendida que será armazenada em um buffer de anéis e gravará a ID de atividade enviada de um cliente no RPC e de operações de lote.</span><span class="sxs-lookup"><span data-stu-id="08228-120">The following is a sample that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
  
```  
  
## <a name="control-file"></a><span data-ttu-id="08228-121">Arquivo de controle</span><span class="sxs-lookup"><span data-stu-id="08228-121">Control File</span></span>  
 <span data-ttu-id="08228-122">No [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], o conteúdo do arquivo de controle do SQL Server Native Client (ctrl.guid.snac11) é:</span><span class="sxs-lookup"><span data-stu-id="08228-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client control file (ctrl.guid.snac11) is:</span></span>  
  
```  
{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}  0x00000000  0   MSDADIAG.ETW  
{2DA81B52-908E-7DB6-EF81-76856BB47C4F}  0xFFFFFFFF  0   SQLNCLI11.1  
```  
  
## <a name="mof-file"></a><span data-ttu-id="08228-123">Arquivo MOF</span><span class="sxs-lookup"><span data-stu-id="08228-123">MOF File</span></span>  
 <span data-ttu-id="08228-124">No [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], o conteúdo do arquivo mof do SQL Server Native Client é:</span><span class="sxs-lookup"><span data-stu-id="08228-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client mof file is:</span></span>  
  
```  
#pragma classflags("forceupdate")  
#pragma namespace ("\\\\.\\Root\\WMI")  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  MSDADIAG.ETW  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F3-3CC6-0B9C-6651-9649CCE5C752}"),  
 DisplayName("msdadiag"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace : Bid2Etw_MSDADIAG_ETW  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextA : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextW : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  SQLNCLI11.1  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B52-908E-7DB6-EF81-76856BB47C4F}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1 : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B53-908E-7DB6-EF81-76856BB47C4F}"),  
 DisplayName("SQLNCLI11.1"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace : Bid2Etw_SQLNCLI11_1  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextA : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextW : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="08228-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="08228-125">See Also</span></span>  
 [<span data-ttu-id="08228-126">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="08228-126">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
