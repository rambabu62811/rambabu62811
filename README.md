mport java.util.Random;

public class NumberPlateGenerator {
    private static final String[] STATE_CODES = {
        "DL", "MH", "KA", "TN", "UP", "RJ", "WB", "GJ", "AP", "BR", "HR", "JK", "KL", "OR", "PB", "AS"
    }; // Add more state codes as needed

    public static void main(String[] args) {
        String numberPlate = generateNumberPlate();
        System.out.println("Generated Indian Number Plate: " + numberPlate);
    }

    public static String generateNumberPlate() {
        Random random = new Random();
        
        // Choose a random state code
        String stateCode = STATE_CODES[random.nextInt(STATE_CODES.length)];

        // Generate two digits for district code
        int districtCode = random.nextInt(100); // 00 to 99

        // Generate two letters for series
        char letter1 = (char) ('A' + random.nextInt(26)); // A-Z
        char letter2 = (char) ('A' + random.nextInt(26)); // A-Z

        // Generate four digits for unique number
        int uniqueNumber = random.nextInt(10000); // 0000 to 9999

        // Format the number plate
        return String.format("%s %02d %c%c %04d", stateCode, districtCode, letter1, letter2, uniqueNumber);
    }
}
