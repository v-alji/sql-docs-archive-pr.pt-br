---
title: Caracteres inválidos e regras de escape | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, invalid characters
- FOR XML clause, escape rules
ms.assetid: f2e9b997-f400-4963-b225-59d46c6b93e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8624a31dea4e97e05da6d86c3c0c518b9c4d0aba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685476"
---
# <a name="invalid-characters-and-escape-rules"></a><span data-ttu-id="2361d-102">Caracteres inválidos e regras de escape</span><span class="sxs-lookup"><span data-stu-id="2361d-102">Invalid Characters and Escape Rules</span></span>
  <span data-ttu-id="2361d-103">Este tópico descreve como caracteres XML inválidos são tratados pela cláusula FOR XML e lista as regras de escape para caracteres inválidos em nomes XML.</span><span class="sxs-lookup"><span data-stu-id="2361d-103">This topic describes how invalid XML characters are handled by the FOR XML clause, and lists the escape rules for characters that are invalid in XML names.</span></span>  
  
## <a name="for-xml-and-invalid-characters"></a><span data-ttu-id="2361d-104">Para XML e caracteres inválidos</span><span class="sxs-lookup"><span data-stu-id="2361d-104">For XML and Invalid Characters</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2361d-105">tem a entidade definida como caracteres XML inválidos quando eles são retornados dentro de consultas FOR XML que não usam a diretiva TYPE.</span><span class="sxs-lookup"><span data-stu-id="2361d-105">entitizes invalid XML characters when they are returned within FOR XML queries that do not use the TYPE directive.</span></span>  
  
 <span data-ttu-id="2361d-106">Embora analisadores compatíveis com o XML 1.0 gerem erros de análise independentemente da entidade desses caracteres estarem definidas ou não, o formulário com entidade definida se alinha melhor com XML 1.1.</span><span class="sxs-lookup"><span data-stu-id="2361d-106">Although XML 1.0 conformant parsers raise parse errors regardless of whether these characters are entitized or not, the entitized form is better aligned with XML 1.1.</span></span> <span data-ttu-id="2361d-107">O formulário com entidade definida também potencialmente se alinha melhor com versões futuras do padrão XML.</span><span class="sxs-lookup"><span data-stu-id="2361d-107">The entitized form is also potentially better aligned with future versions of the XML standard.</span></span> <span data-ttu-id="2361d-108">Além disso, ele simplifica a depuração, porque o ponto de código do caractere inválido se torna visível.</span><span class="sxs-lookup"><span data-stu-id="2361d-108">Additionally, it makes debugging simpler, because the code point of the invalid character becomes visible.</span></span>  
  
 <span data-ttu-id="2361d-109">Para usuários de ferramentas XML, nenhuma solução alternativa é necessária, porque o analisador XML falha de qualquer maneira no ponto onde os caracteres inválidos ocorrem no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="2361d-109">For users of XML tools, no workaround is required, because the XML parser will fail either way at the point where the invalid characters occur in the data stream.</span></span> <span data-ttu-id="2361d-110">Se você usar ferramentas não XML, essa alteração pode exigir que você atualize sua lógica de programação para pesquisar esses caracteres como valores com entidade definida.</span><span class="sxs-lookup"><span data-stu-id="2361d-110">If you use non-XML tools, this change can require you to update your programming logic to search for these characters as entitized values.</span></span>  
  
 <span data-ttu-id="2361d-111">A definição da entidade dos seguintes caracteres de espaço em branco é feita de maneira diferente em consultas FOR XML para preservar sua presença por meio de viagem de ida e volta:</span><span class="sxs-lookup"><span data-stu-id="2361d-111">The following white space characters are entitized differently in FOR XML queries to preserve their presence through round-tripping:</span></span>  
  
-   <span data-ttu-id="2361d-112">Em atributos e conteúdo de elemento: **hex(0D)** (retorno de carro)</span><span class="sxs-lookup"><span data-stu-id="2361d-112">In element content and attributes: **hex(0D)** (carriage return)</span></span>  
  
-   <span data-ttu-id="2361d-113">Em conteúdo de atributo: **hex(09)** (guia), **hex(0A)** (alimentação de linha)</span><span class="sxs-lookup"><span data-stu-id="2361d-113">In attribute content: **hex(09)** (tab), **hex(0A)** (line feed)</span></span>  
  
 <span data-ttu-id="2361d-114">Esses caracteres são preservados na saída e um analisador não os normalizará.</span><span class="sxs-lookup"><span data-stu-id="2361d-114">These characters are preserved in output, and a parser will not normalize them.</span></span>  
  
## <a name="escape-rules"></a><span data-ttu-id="2361d-115">Regras de escape</span><span class="sxs-lookup"><span data-stu-id="2361d-115">Escape Rules</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2361d-116">nomes que contêm caracteres que são inválidos em nomes XML, como espaços, são convertidos em nomes XML de uma maneira na qual os caracteres inválidos são convertidos em codificação de entidade numérica de escape.</span><span class="sxs-lookup"><span data-stu-id="2361d-116">names that contain characters that are invalid in XML names, such as spaces, are translated into XML names in a way in which the invalid characters are translated into escaped numeric entity encoding.</span></span>  
  
 <span data-ttu-id="2361d-117">Há apenas dois caracteres não alfabéticos que podem ocorrer dentro de um nome XML: dois pontos (:) e sublinhado (_).</span><span class="sxs-lookup"><span data-stu-id="2361d-117">There are only two non-alphabetic characters that can occur within an XML name: the colon (:) and the underscore (_).</span></span> <span data-ttu-id="2361d-118">Como o dois pontos já é reservado para namespaces, o sublinhado é escolhido como o caractere de escape.</span><span class="sxs-lookup"><span data-stu-id="2361d-118">Because the colon is already reserved for namespaces, the underscore is chosen as the escape character.</span></span> <span data-ttu-id="2361d-119">As regras de escape que são usadas para codificação são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="2361d-119">Following are the escape rules that are used for encoding:</span></span>  
  
-   <span data-ttu-id="2361d-120">Qualquer caractere UCS-2 que não seja um caractere de nome XML válido, de acordo com a especificação do XML 1.0, tem o escape feito como _xHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="2361d-120">Any UCS-2 character that is not a valid XML name character, according to the XML 1.0 specification, is escaped as _xHHHH\_.</span></span> <span data-ttu-id="2361d-121">O HHHH representa o código UCS-2 hexadecimal de quatro dígitos do caractere na ordem do primeiro bit mais significativo.</span><span class="sxs-lookup"><span data-stu-id="2361d-121">The HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="2361d-122">Por exemplo, o nome da tabela **Order Details** é codificado como Order_x0020_Details.</span><span class="sxs-lookup"><span data-stu-id="2361d-122">For example, the table name **Order Details** is encoded as Order_x0020_Details.</span></span>  
  
-   <span data-ttu-id="2361d-123">Caracteres que não se ajustam no realm do UCS-2 (as adições de UCS-4 do intervalo de U+00010000 a U+0010FFFF) são codificadas como _xHHHHHHHH\_.</span><span class="sxs-lookup"><span data-stu-id="2361d-123">Characters that do not fit into the UCS-2 realm (the UCS-4 additions of the range U+00010000 to U+0010FFFF) are encoded as _xHHHHHHHH\_.</span></span> <span data-ttu-id="2361d-124">O HHHHHHHH representa a codificação UCS-4 hexadecimal de oito dígitos do caractere, se em modo de compatibilidade com versões anteriores do SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="2361d-124">The HHHHHHHH stands for the eight-digit hexadecimal UCS-4 encoding of the character, if under SQL Server 2000 backward compatibility mode.</span></span> <span data-ttu-id="2361d-125">Caso contrário, os caracteres são codificados como _xHHHHHH\_, para se alinharem com o padrão ISO.</span><span class="sxs-lookup"><span data-stu-id="2361d-125">Otherwise, the characters are encoded as_xHHHHHH\_, in order to align with the ISO standard.</span></span>  
  
-   <span data-ttu-id="2361d-126">O caractere de sublinhado não precisa ter escape definido a menos que ele seja seguido pelo caractere x.</span><span class="sxs-lookup"><span data-stu-id="2361d-126">The underscore character does not have to be escaped unless it is followed by the character x.</span></span> <span data-ttu-id="2361d-127">Por exemplo, o nome da tabela **Order_Details** não é codificado.</span><span class="sxs-lookup"><span data-stu-id="2361d-127">For example, the table name **Order_Details** is not encoded.</span></span>  
  
-   <span data-ttu-id="2361d-128">O dois pontos em identificadores não tem escape definido como um resultado, o elemento namespace e os nomes dos atributos podem ser gerados pela consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="2361d-128">The colon in identifiers is not escaped As a result, the namespace element and attribute names can be generated by the FOR XML query.</span></span> <span data-ttu-id="2361d-129">Por exemplo, a consulta a seguir gera um atributo de namespace que tem um dois pontos no nome:</span><span class="sxs-lookup"><span data-stu-id="2361d-129">For example, the following query generates a namespace attribute that has a colon in the name:</span></span>  
  
    ```  
    SELECT 'namespace-urn' as 'xmlns:namespace',   
     1 as 'namespace:a'   
    FOR XML RAW  
    ```  
  
     <span data-ttu-id="2361d-130">A consulta produz este resultado:</span><span class="sxs-lookup"><span data-stu-id="2361d-130">The query produces this result:</span></span>  
  
    ```  
    <row xmlns:namespace="namespace-urn" namespace:a="1"/>  
    ```  
  
     <span data-ttu-id="2361d-131">Observe que WITH XMLNAMESPACES é a maneira recomendada para adicionar namespaces XML.</span><span class="sxs-lookup"><span data-stu-id="2361d-131">Note that WITH XMLNAMESPACES is the recommended way to add XML namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2361d-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2361d-132">See Also</span></span>  
 [<span data-ttu-id="2361d-133">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2361d-133">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
