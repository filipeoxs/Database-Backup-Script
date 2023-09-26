import psycopg2
import os

def backup_database():
    """
    Backups a database to a specified file.

    Returns:
        The status of the backup.
    """

    database = input("Enter the database name: ")
    user = input("Enter the database user: ")
    password = input("Enter the database password: ")
    host = input("Enter the database host: ")

    connection = psycopg2.connect(database=database, user=user, password=password, host=host)
    cursor = connection.cursor()

    cursor.execute("SELECT pg_dumpall(format='custom', data_only=True)")
    backup_data = cursor.fetchone()  # Use fetchone() para obter uma única linha de resultado

    # Define o caminho para o arquivo de backup
    backup_file_path = "caminho/para/seu/backup.backup"

    with open(backup_file_path, "wb") as backup_file:
        backup_file.write(backup_data)

    connection.close()

    return "Backup successful"

if __name__ == "__main__":
    status = backup_database()
    print(status)
