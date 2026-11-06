# Meu Caixa

Aplicativo web simples para organizar o orçamento mensal: você informa seu salário e seus gastos, e o app mostra quanto sobra, quanto vale a pena guardar e de quanto deve ser sua reserva de emergência.

Não conecta a bancos e não pede lançamento de gastos diários. Você informa valores mensais estimados, e a conta é feita na hora.

## O que ele faz

**Aba Orçamento**
- Você digita o salário líquido (o que cai na conta).
- Lista seus gastos mensais em dois grupos: **essenciais** e **desejos**. Dá para adicionar, renomear e remover itens.
- Mostra quanto sobra no fim do mês e compara sua situação com a referência 50/30/20 (até 50% em essenciais, até 30% em desejos e pelo menos 20% para guardar).

**Aba Investir**
- Calcula a **reserva de emergência**: gastos essenciais multiplicados por 3, 6 ou 12 meses, à sua escolha.
- Mostra quanto você já tem guardado e quanto falta.
- Sugere guardar 20% do salário por mês, mas **a decisão é sempre do usuário**: ele define o valor e vê em quantos meses completa a reserva.
- Traz orientações gerais sobre onde manter a reserva.

> As sugestões são educativas e genéricas. Não são recomendação de investimento personalizada. Para decisões específicas, procure um profissional certificado.

## Como funciona o salvamento

- **Sem Supabase configurado:** os dados ficam apenas no navegador do aparelho (localStorage).
- **Com Supabase configurado:** o usuário entra com e-mail (link de acesso, sem senha) e os dados são gravados na nuvem, ligados à conta dele. Cada pessoa só enxerga os próprios dados, graças ao RLS (Row Level Security) do Postgres.

## Tecnologias

- HTML, CSS e JavaScript puro, em um único arquivo (`index.html`)
- [Supabase](https://supabase.com) (Auth e Postgres)
- Hospedagem estática (por exemplo, Vercel)

## Privacidade

O app guarda apenas o que o usuário digita (salário, valores de gastos e metas). Os dados ficam ligados ao e-mail de login e protegidos por RLS. Quem administra o projeto no Supabase consegue ver os registros pelo painel; se você pretende ter usuários reais, informe isso a eles e considere uma política de privacidade e a opção de excluir a conta, conforme a LGPD.

## Limitações conhecidas

- No plano gratuito do Supabase, projetos sem uso por cerca de uma semana podem ser pausados e precisam ser reativados no painel.
- Os valores são estimativas mensais informadas pelo usuário; o app não lê extratos nem contas bancárias.


