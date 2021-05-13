	# класс выполняет две задачи: сохранить и получить имя

	class  User:
		def __init__(self, name: str):
			self.name = name

		def get_name(self) -> str:
			pass

		def save(self, user: User):
			pass

Из-за того что класс выполняет две задачи он становится более зависимым что усложняет внесение изменений в код.

Верное решение:

	class User:
		def __init__(self, name: str):
				self.name = name

		def get_name(self):
			pass

	class UserDB:
		def get_user(self, id) -> User:
			#Использует класс User для получения имени
			pass

		def save(self, user: User):
			pass


>Для объединения классов которые следуют принципу единой ответственности часто применяют паттерн [[фасад]].




[[Single Responsibility Principle]] [[S.O.L.I.D]]