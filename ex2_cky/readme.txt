#### ����ȯ�� ####
OS : ubuntu 18.0.4 (using docker)
Arch : 64 bit
IDE : Jupyter lab


#### ������� ####
Python 3.7.2


#### �����̺귯�� ####
����


#### ������ ####
cky_parser.py�� grammar.txt �� input.txt�� ���� ������ �ΰ� ���� ��ɾ�� ����
python cky_parser.py

�����ϸ� input.txt�� �غ�� ������ CKY Parsing �Ǿ� output.txt���� Parse Tree �����, used_grammar.txt���� �м��� ���� �������� �ε��� �αװ� ����ȴ�.


####  ������ ####
used_grammar.txt: ���庰�� �м��� ���� ������ ���� �ε��� �α�
(Symbol, [(Left Node Index, Right Node Index),(..)]) �������� Shared-Packed Tree�� ���� ������ �����. 
���� ����� ��� Index ��ȣ ��� �ܾ ���.

output.txt: ���庰�� �м� �Ϸ�� Parse Tree�� ���
(Symbol, (Left Node) (Right Node)) �������� �����.

cky_parser.html: �ҽ��ڵ�, ���庰�� ���� ���������� �ε��� �α�, �м��Ϸ�� Parse Tree ���, CKY Parse Table�� ��� ��ϵǾ� ����


#### ������� ####
1. used_grammar.txt�� output.txt�� ��µǴ� ������ �ֿܼ����� �����ϰ� ��µȴ�.

2. 257���ο� trees = parser.parse(line, "used_grammar.txt", True) �� ������ �Ķ���͸� True�� �ָ� �ܼ� �� table.txt�� �� ���忡 ���� CKY Parse Table�� ��µȴ�. 

3. used_grammar.txt���� "# packed !" �� ���ʿ� �پ��ִ� ���� ���, ������ �̹� Parsing �Ǿ� Table�� ��尡 �߰� �Ǿ����� �ش� ����� Sub Parse Tree�� ���� ������ ��츦 ��Ÿ����. (�� Packing�Ǵ� ����) 
���� �ش� ���� �ε����� ������ �����ߴ� �ε��� ��ȣ�� �����ϴ�. 

4. �ҽ��ڵ� �� ����� �ؽ�Ʈ���� ���ڵ��� ��� UTF-8�� ������, ��������� ���๮�ڴ� Unix-style '\n' �� ������. 
���� ��� �ؽ�Ʈ������ ������ ȯ�濡�� �޸����̾ƴ�, �����е� �Ǵ� ��Ÿ �ؽ�Ʈ������(Sublime text ��)�� Ȯ���ʿ�!

5. �ҽ��ڵ忡 �ּ����� �ڵ弳���� ��õǾ�����

