---
title: Restrição de atribuição de partícula exclusiva | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
f1_keywords:
- unique particle attribution
helpviewer_keywords:
- schema collections [SQL Server], unique particle attribution
- XML schema collections [SQL Server], unique particle attribution
- UPA constraint rule
- unique particle attribution constraint rule
ms.assetid: 6bb879e9-a5ee-402e-94e4-fe8cec5966b0
author: rothja
ms.author: jroth
ms.openlocfilehash: 7416aa4ea14539f3bf633207768783aa439ec818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678665"
---
# <a name="unique-particle-attribution-constraint"></a><span data-ttu-id="ab5b4-102">Restrição de atribuição de partícula exclusiva</span><span class="sxs-lookup"><span data-stu-id="ab5b4-102">Unique Particle Attribution Constraint</span></span>
  <span data-ttu-id="ab5b4-103">Em XSD, modelos de conteúdo complexos são restritos pela regra de restrição UPA (atribuição de partícula exclusiva).</span><span class="sxs-lookup"><span data-stu-id="ab5b4-103">In XSD, complex content models are constrained by the unique particle attribution (UPA) constraint rule.</span></span> <span data-ttu-id="ab5b4-104">Essa regra requer que cada elemento em um documento da instância corresponda sem-ambiguidade a exatamente uma partícula `<xsd:element>` ou `<xsd:any>` no modelo de conteúdo de seu pai.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-104">This rule requires that each element in an instance document correspond unambiguously to exactly one `<xsd:element>` or `<xsd:any>` particle in its parent's content model.</span></span> <span data-ttu-id="ab5b4-105">Qualquer esquema que contenha um tipo com um modelo de conteúdo potencialmente ambíguo é rejeitado.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-105">Any schema that contains a type with a potentially ambiguous content model is rejected.</span></span>  
  
 <span data-ttu-id="ab5b4-106">Os casos mais comuns de ambiguidade são caracteres curinga `<xsd:any>` e partículas que têm intervalos variáveis de ocorrências, como minOccurs < maxOccurs.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-106">The most common causes of ambiguity are `<xsd:any>` wildcard characters and particles that have variable occurrence ranges, such as minOccurs < maxOccurs.</span></span> <span data-ttu-id="ab5b4-107">Por exemplo, o modelo de conteúdo a seguir é ambíguo porque um elemento <`e1`> pode corresponder ao elemento `<xsd:element>` ou `<xsd:any>`.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-107">For example, the following content model is ambiguous, because an <`e1`> element could match either the `<xsd:element>` or the `<xsd:any>` element.</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
            <xsd:element name="e1"/>  
            <xsd:any namespace="##any"/>  
        </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="ab5b4-108">O modelo de conteúdo seguinte também é ambíguo:</span><span class="sxs-lookup"><span data-stu-id="ab5b4-108">The following content model is also ambiguous:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:sequence>  
            <xsd:element name="e1" maxOccurs="2"/>  
            <xsd:element name="e2" minOccurs="0"/>  
            <xsd:element name="e1"/>  
        </xsd:sequence>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="ab5b4-109">Embora seja possível validar um documento como `<root><e1/><e2/><e1/></root>` de maneira não ambígua, um documento como `<root><e1/><e1/></root>` não pode ser validado, porque não está claro para qual `<xsd:element>` o segundo `<e1/>` corresponde.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-109">Although a document such as `<root><e1/><e2/><e1/></root>` can be validated unambiguously, a document such as `<root><e1/><e1/></root>` cannot, because it is not clear to which `<xsd:element>` the second `<e1/>` corresponds.</span></span> <span data-ttu-id="ab5b4-110">Embora alguns documentos possam ser validados de maneira não ambígua, o esquema será rejeitado por causa do potencial de ambiguidade.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-110">Even though some documents can be validated unambiguously, the schema will be rejected, because of the potential for ambiguity.</span></span>  
  
 <span data-ttu-id="ab5b4-111">Observe que para que um modelo de conteúdo seja válido, deve ser possível validar todas as suas instâncias de maneira não ambígua sem olhar adiante.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-111">Note that for a content model to be valid, it must be possible to validate any instance unambiguously without looking ahead.</span></span> <span data-ttu-id="ab5b4-112">Por exemplo, considere o seguinte modelo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="ab5b4-112">For example, consider the following content model:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e2"/>  
           </xsd:sequence>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e3"/>  
           </xsd:sequence>  
       </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="ab5b4-113">Para um documento como `<root><e1/><e3/></root>`, a sequência `<e1/><e3/>` corresponde de maneira não ambígua à segunda `<xsd:sequence>`.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-113">For a document such as `<root><e1/><e3/></root>`, the sequence `<e1/><e3/>` unambiguously matches the second `<xsd:sequence>`.</span></span> <span data-ttu-id="ab5b4-114">No entanto, como o `<xsd:element>` ao qual `<e1/>` corresponde não pode ser determinado sem olhar adiante para `<e3/>`, o modelo de conteúdo viola a regra de restrição de UPA.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-114">However, because the `<xsd:element>` to which `<e1/>` corresponds cannot be determined without looking ahead to `<e3/>`, the content model violates the UPA constraint rule.</span></span>  
  
## <a name="finding-more-information"></a><span data-ttu-id="ab5b4-115">Descobrindo mais informações</span><span class="sxs-lookup"><span data-stu-id="ab5b4-115">Finding More Information</span></span>  
 <span data-ttu-id="ab5b4-116">O documento a seguir é publicado pelo World Wide Web Consortium (W3C) e contém a descrição técnica da restrição de atribuição de partícula ambígua.</span><span class="sxs-lookup"><span data-stu-id="ab5b4-116">The following document is published by the World Wide Web Consortium (W3C) and contains the technical description of the unique particle attribution constraint:</span></span>  
  
 <span data-ttu-id="ab5b4-117">"Parte 1 do esquema XML: segunda edição das estruturas, recomendação proposta editada do W3C":</span><span class="sxs-lookup"><span data-stu-id="ab5b4-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation":</span></span>  
  
-   <span data-ttu-id="ab5b4-118">Seção 3.8.6: restrições em componentes de esquema do grupo de modelos</span><span class="sxs-lookup"><span data-stu-id="ab5b4-118">Section 3.8.6: Constraints on Model Group Schema Components</span></span>  
  
-   <span data-ttu-id="ab5b4-119">Apêndice H: análise da restrição de atribuição de partícula exclusiva (não normativa)</span><span class="sxs-lookup"><span data-stu-id="ab5b4-119">Appendix H: Analysis of the Unique Particle Attribution Constraint (non-normative)</span></span>  
  
 <span data-ttu-id="ab5b4-120">Para consultar o documento, visite [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span><span class="sxs-lookup"><span data-stu-id="ab5b4-120">To see the document, visit [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab5b4-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ab5b4-121">See Also</span></span>  
 [<span data-ttu-id="ab5b4-122">Coleções de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ab5b4-122">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
