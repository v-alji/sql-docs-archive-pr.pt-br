---
title: Gerenciando conexões e sessões (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statefulness [XML for Analysis]
- statelessness [XML for Analysis]
- XML for Analysis, sessions
- states [XML for Analysis]
- XMLA, sessions
- sessions [XML for Analysis]
ms.assetid: b83bb3ff-09be-4fda-9d1d-6248e04ffb21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bfe876f6874193fd0885f16d91caa9f6fe8b172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572772"
---
# <a name="managing-connections-and-sessions-xmla"></a><span data-ttu-id="18666-102">Gerenciando conexões e sessões (XMLA)</span><span class="sxs-lookup"><span data-stu-id="18666-102">Managing Connections and Sessions (XMLA)</span></span>
  <span data-ttu-id="18666-103">A *monitoração* é uma condição durante a qual o servidor preserva a identidade e o contexto de um cliente entre chamadas de método.</span><span class="sxs-lookup"><span data-stu-id="18666-103">*Statefulness* is a condition during which the server preserves the identity and context of a client between method calls.</span></span> <span data-ttu-id="18666-104">*Sem estado* é uma condição durante a qual o servidor não se lembra da identidade e do contexto de um cliente após a conclusão de uma chamada de método.</span><span class="sxs-lookup"><span data-stu-id="18666-104">*Statelessness* is a condition during which the server does not remember the identity and context of a client after a method call finishes.</span></span>  
  
 <span data-ttu-id="18666-105">Para fornecer estado, XML for Analysis (XMLA) dá suporte a *sessões* que permitem que uma série de instruções seja executada juntas.</span><span class="sxs-lookup"><span data-stu-id="18666-105">To provide statefulness, XML for Analysis (XMLA) supports *sessions* that allow a series of statements to be performed together.</span></span> <span data-ttu-id="18666-106">Um exemplo de uma dessas séries de instruções seria a criação de um membro calculado a ser usado em consultas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="18666-106">An example of such a series of statements would be the creation of a calculated member that is to be used in subsequent queries.</span></span>  
  
 <span data-ttu-id="18666-107">Em geral, as sessões em XMLA seguem o comportamento a seguir, descrito pela especificação do OLE DB 2.6:</span><span class="sxs-lookup"><span data-stu-id="18666-107">In general, sessions in XMLA follow the following behavior outlined by the OLE DB 2.6 specification:</span></span>  
  
-   <span data-ttu-id="18666-108">As sessões definem o escopo do contexto de comando e de transação.</span><span class="sxs-lookup"><span data-stu-id="18666-108">Sessions define transaction and command context scope.</span></span>  
  
-   <span data-ttu-id="18666-109">Vários comandos podem ser executados no contexto de uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="18666-109">Multiple commands can be run in the context of a single session.</span></span>  
  
-   <span data-ttu-id="18666-110">O suporte para transações no contexto XMLA é por meio de comandos específicos do provedor enviados com o método [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="18666-110">Support for transactions in the XMLA context is through provider-specific commands sent with the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
 <span data-ttu-id="18666-111">O XMLA define uma forma de suportar sessões em um ambiente da Web em um modo similar à abordagem usada pelo protocolo DAV (Distributed Authoring and Versioning) para a implementação do bloqueio em um ambiente flexível.</span><span class="sxs-lookup"><span data-stu-id="18666-111">XMLA defines a way to support sessions in a Web environment in a mode similar to the approach used by the Distributed Authoring and Versioning (DAV) protocol to implement locking in a loosely coupled environment.</span></span> <span data-ttu-id="18666-112">Esta implementação se compara ao DAV, já que o provedor pode fazer uma sessão expirar por vários motivos (por exemplo, um tempo limite ou um erro de conexão).</span><span class="sxs-lookup"><span data-stu-id="18666-112">This implementation parallels DAV in that the provider is allowed to expire sessions for various reasons (for example, a timeout or connection error).</span></span> <span data-ttu-id="18666-113">Quando as sessões forem suportadas, os serviços Web deverão estar atentos e prontos para lidarem com conjuntos de comandos interrompidos que deverão ser reiniciados.</span><span class="sxs-lookup"><span data-stu-id="18666-113">When sessions are supported, Web services must be aware and ready to handle interrupted sets of commands that must be restarted.</span></span>  
  
 <span data-ttu-id="18666-114">A especificação do protocolo SOAP do W3C (World Wide Web Consortium) recomenda a utilização de cabeçalhos SOAP para a criação de novos protocolos sobre mensagens SOAP.</span><span class="sxs-lookup"><span data-stu-id="18666-114">The World Wide Web Consortium (W3C) Simple Object Access Protocol (SOAP) specification recommends using SOAP headers for building up new protocols on top of SOAP messages.</span></span> <span data-ttu-id="18666-115">A tabela a seguir lista os elementos e os atributos de cabeçalho SOAP definidos pelo XMLA para iniciar, manter e fechar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="18666-115">The following table lists the SOAP header elements and attributes that XMLA defines for initiating, maintaining, and closing a session.</span></span>  
  
|<span data-ttu-id="18666-116">Cabeçalho SOAP</span><span class="sxs-lookup"><span data-stu-id="18666-116">SOAP header</span></span>|<span data-ttu-id="18666-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="18666-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="18666-118">BeginSession</span><span class="sxs-lookup"><span data-stu-id="18666-118">BeginSession</span></span>|<span data-ttu-id="18666-119">Este cabeçalho solicita que o provedor crie uma sessão nova.</span><span class="sxs-lookup"><span data-stu-id="18666-119">This header requests the provider to create a new session.</span></span> <span data-ttu-id="18666-120">O provedor deve responder criando uma sessão nova e retornando a ID de sessão como parte do cabeçalho Session na resposta SOAP.</span><span class="sxs-lookup"><span data-stu-id="18666-120">The provider should respond by constructing a new session and returning the session ID as part of the Session header in the SOAP response.</span></span>|  
|<span data-ttu-id="18666-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="18666-121">SessionId</span></span>|<span data-ttu-id="18666-122">A área de valor contém a ID de sessão que deve ser usada em cada chamada de método para o resto da sessão.</span><span class="sxs-lookup"><span data-stu-id="18666-122">The value area contains the session ID that must be used in each method call for the rest of the session.</span></span> <span data-ttu-id="18666-123">O provedor na resposta de SOAP envia esta marca e o cliente também deve enviar este atributo com cada elemento do cabeçalho Session.</span><span class="sxs-lookup"><span data-stu-id="18666-123">The provider in the SOAP response sends this tag and the client must also send this attribute with each Session header element.</span></span>|  
|<span data-ttu-id="18666-124">Session</span><span class="sxs-lookup"><span data-stu-id="18666-124">Session</span></span>|<span data-ttu-id="18666-125">Para cada chamada de método ocorrida na sessão, este cabeçalho deverá ser usado e a ID de sessão deverá ser incluída na área de valor do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="18666-125">For every method call that occurs in the session, this header must be used, and the session ID must be included in the value area of the header.</span></span>|  
|<span data-ttu-id="18666-126">EndSession</span><span class="sxs-lookup"><span data-stu-id="18666-126">EndSession</span></span>|<span data-ttu-id="18666-127">Para finalizar a sessão, use este cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="18666-127">To terminate the session, use this header.</span></span> <span data-ttu-id="18666-128">A ID de sessão deve ser incluída com a área de valor.</span><span class="sxs-lookup"><span data-stu-id="18666-128">The session ID must be included with the value area.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="18666-129">A ID de sessão não garante que uma sessão permanecerá válida.</span><span class="sxs-lookup"><span data-stu-id="18666-129">A session ID does not guarantee that a session stays valid.</span></span> <span data-ttu-id="18666-130">Se a sessão expirar (por exemplo, se o tempo limite for alcançado ou se a conexão for interrompida), o provedor poderá optar por encerrar e reverter as ações dessa sessão.</span><span class="sxs-lookup"><span data-stu-id="18666-130">If the session expires (for example, if it times out or the connection is lost), the provider can choose to end and roll back that session's actions.</span></span> <span data-ttu-id="18666-131">Como resultado, todas as chamadas de método subsequentes feitas do cliente em uma ID de sessão falharão com um erro que indicará uma sessão inválida.</span><span class="sxs-lookup"><span data-stu-id="18666-131">As a result, all subsequent method calls from the client on a session ID fail with an error signaling a session that is not valid.</span></span> <span data-ttu-id="18666-132">Um cliente deve lidar com esta condição e estar preparado para reenviar as chamadas de método de sessão desde o princípio.</span><span class="sxs-lookup"><span data-stu-id="18666-132">A client should handle this condition and be prepared to resend the session method calls from the beginning.</span></span>  
  
## <a name="legacy-code-example"></a><span data-ttu-id="18666-133">Exemplo de código herdado</span><span class="sxs-lookup"><span data-stu-id="18666-133">Legacy Code Example</span></span>  
 <span data-ttu-id="18666-134">O exemplo a seguir mostra como as sessões são suportadas.</span><span class="sxs-lookup"><span data-stu-id="18666-134">The following example shows how sessions are supported.</span></span>  
  
1.  <span data-ttu-id="18666-135">Para iniciar a sessão, acrescente um cabeçalho BeginSession em SOAP à chamada de método XMLA a partir do cliente.</span><span class="sxs-lookup"><span data-stu-id="18666-135">To begin the session, add a BeginSession header in SOAP to the outbound XMLA method call from the client.</span></span> <span data-ttu-id="18666-136">Inicialmente, a área de valor estará em branco, já que a ID de sessão ainda não é conhecida.</span><span class="sxs-lookup"><span data-stu-id="18666-136">The value area is initially blank because the session ID is not yet known.</span></span>  
  
    ```  
    <SOAP-ENV:Envelope  
       xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
       SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
       <SOAP-ENV:Header>  
          <XA:BeginSession  
             xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
             xsi:type="xsd:int"  
             mustUnderstand="1"/>  
       </SOAP-ENV:Header>  
       <SOAP-ENV:Body>  
          ...<!-- Discover or Execute call goes here.-->  
       </SOAP-ENV:Body>  
    </SOAP-ENV:Envelope>  
    ```  
  
2.  <span data-ttu-id="18666-137">A mensagem de resposta SOAP do provedor inclui a ID de sessão na área de cabeçalho de retorno, usando a marca de cabeçalho XMLA \<SessionId> .</span><span class="sxs-lookup"><span data-stu-id="18666-137">The SOAP response message from the provider includes the session ID in the return header area, using the XMLA header tag \<SessionId>.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
3.  <span data-ttu-id="18666-138">O cabeçalho Session deve ser adicionado a cada chamada de método da sessão, com a ID de sessão retornada do provedor.</span><span class="sxs-lookup"><span data-stu-id="18666-138">For each method call in the session, the Session header must be added, containing the session ID returned from the provider.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
4.  <span data-ttu-id="18666-139">Quando a sessão for concluída, a \<EndSession> marca será usada, contendo o valor de ID de sessão relacionado.</span><span class="sxs-lookup"><span data-stu-id="18666-139">When the session is complete, the \<EndSession> tag is used, containing the related session ID value.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:EndSession  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          xsi:type="xsd:int"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="18666-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="18666-140">See Also</span></span>  
 [<span data-ttu-id="18666-141">Desenvolvendo com XMLA no Analysis Services</span><span class="sxs-lookup"><span data-stu-id="18666-141">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
